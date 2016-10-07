# Skróty artykułów na liście wyszukiwania
2016-09-23

Na liście wyników wyszukiwania portletu "search" dla różnych typów treści pojawiają się różne abstrakty:
- WebContent
    - "Podsumowanie" (Descrption) - jeżeli nie jest puste
    - kontekst(y) wyszukiwanej frazy, skrócone do 200 znaków
- Użytkownik
- Plik z DL

JSP odpowiedzialny za wyświetlanie skrótów na liście wyników:
https://github.com/liferay/liferay-portal/blob/6.2.x/portal-web/docroot/html/portlet/search/main_search_result_form.jsp#L165

Z analizy klasy JournalArticleIndexer wynika, że za generowanie skrótów odpowiedzialne są dwie różne metody
- getBasicContentSummary() dla zwykłego webcontentu (która już z Lucene'a dostaje ładnie przygotowany skrót z konteklstem wyszukiwanej frazy)
- getDDMContentSummary() dla pozostałych struktur (która już nie generuje takiego ładnego skrótu)

Zmodyfikować mechanizm wyświetlania skrotu w wynikach wyszukiwania można na kilka sposobów (od najładnieszego i najtrudnieszego, do najgorszego):
1. Ext - przy pomocy exta modyfikujemy Indexera (i JournalArticleLocalServiceImpl), aby pobierał z wyszukiwarki "ładne" skróty także dla DDM-ów
2. Hook "model-listener" na JournalArticle i przy tworzeniu artykułu generujemy "description" na podstawie treści
  1. Rozszerzamy klasę BaseModelListener<JournalArticle>"
  2. Wymaga przeparsowania zawartości artkułu przy pomocy SAXParsera, np:
    ...
```java
        Document doc = SAXReaderUtil.read(journalArticle.getContentByLocale(LocaleUtil.toLanguageId(locale)));
            List<Node> nodes = doc.selectNodes("//dynamic-element[@name='zawartosc' or @name='odpowiedz']/dynamic-content");

            for (Node node : nodes) {
                nodesContent.append(node.getText());
                nodesContent.append(" ");
            }
            if (nodesContent.length()>0)
                nodesContent.setLength(nodesContent.length() - 1);

            content = nodesContent.toString();
``` 
...           
3. Hook JSP - po prostu modyfikujemy zawartość "skrótu" tuż przed wyświetleniem w pliku JSP