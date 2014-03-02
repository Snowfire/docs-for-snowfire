Quote modifications
===================

This is a collection of nifty code snippets to modify the quote block

The default CSS
---------------

```css
.column.quote blockquote,
.column.quote_synced blockquote {
  padding: 0px;
  font-style: normal;
  position: relative;
  border-left: 0;
  border-radius: 10px;
  width: 80%;
  float: left;
  box-sizing: border-box;
  padding: 10px 20px 10px 0px;
}

.column.quote blockquote:after, .column.quote blockquote:before,
.column.quote_synced blockquote:after,
.column.quote_synced blockquote:before {
  top: 100%;
  border: solid transparent;
  content: " ";
  height: 0;
  width: 0;
  position: absolute;
  pointer-events: none;
}

.column.quote blockquote:after,
.column.quote_synced blockquote:after {
  border-top-color: #fdfdfd;
  border-width: 12px;
  left: 50%;
  margin-left: -12px;
}

.column.quote blockquote:before,
.column.quote_synced blockquote:before {
  border-top-color: rgba(200, 200, 200, 0.8);
  border-width: 13px;
  left: 50%;
  margin-left: -13px;
}

.column.quote blockquote p,
.column.quote_synced blockquote p {
  width: 100%;
  font-style: normal;
  font-size: 14px;
  margin-bottom: 0px;
}

.column.quote blockquote p.author,
.column.quote_synced blockquote p.author {
  margin: 10px 0 0 0;
  color: #888 !important;
  font-size: 13px;
}

.column.quote .image,
.column.quote_synced .image {
  box-sizing: border-box;
  float: left;
  width: 15%;
  margin: 5px 10px 10px 0px;
  text-align: center;
}

.column.quote .image img,
.column.quote_synced .image img {
  border-radius: 70px;
}

.column.quote blockquote:before,
.column.quote blockquote:after,
.column.quote q:before,
.column.quote q:after,
.column.quote_synced blockquote:before,
.column.quote_synced blockquote:after,
.column.quote_synced q:before,
.column.quote_synced q:after {
  content: '';
  content: none;
}
```
