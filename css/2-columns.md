# 2 columns

## 2 columns, left fluid

### HTML
```
<div class="container">
    <div class="right">
        right content fixed width
    </div>
    <div class="left">
        left content flexible width
    </div>
</div>
```

### CSS
```
.container {
   height: auto;
   overflow: hidden;
}

.right {
    width: 180px;
    float: right;
    background: #aafed6;
}

.left {
    float: none; /* not needed, just for clarification */
    background: #e8f6fe;
    /* the next props are meant to keep this block independent from the other floated one */
    width: auto;
    overflow: hidden;
}​​
```