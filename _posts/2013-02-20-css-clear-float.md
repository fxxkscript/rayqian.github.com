title: CSS清除浮动
date: 2013-02-20 17:14:27
tags: css
categories: tech
---

1. Micro-Clearfix

  <http://nicolasgallagher.com/micro-clearfix-hack/>
  
  ```
  
   * For modern browsers
   * 1. The space content is one way to avoid an Opera bug when the
   *    contenteditable attribute is included anywhere else in the document.
   *    Otherwise it causes space to appear at the top and bottom of elements
   *    that are clearfixed.
   * 2. The use of `table` rather than `block` is only necessary if using
   *    `:before` to contain the top-margins of child elements.
   */
  .cf:before,
  .cf:after {
      content: " "; /* 1 */
      display: table; /* 2 */
  }

  .cf:after {
      clear: both;
  }

  /**
   * For IE 6/7 only
   * Include this rule to trigger hasLayout and contain floats.
   */
  .cf {
      *zoom: 1;
  }
  
  ```


2. Overflow

  <http://www.quirksmode.org/css/clearing.html>
  
  ```
  .container {
      overflow: hidden;
      display: inline-block; /* Necessary to trigger "hasLayout" in IE */
      display: block; /* Sets element back to block */
  }
  ```
  
  ```
  .container {
      overflow: hidden; /* Clearfix! */
      zoom: 1;  /* Triggering "hasLayout" in IE */
      display: block; /* Element must be a block to wrap around contents. Unnecessary if only using block-level elements. */
  }
  ```
  
  ```
  .container {
      overflow: hidden;
      _overflow: visible; /* for IE */
      _zoom: 1; /* for IE */
  }
  ```
3. ":after"伪元素

  ```
  .container {
      display: inline-block;
  }
  .container:after {
      content: " ";
      display: block;
      height: 0;
      clear: both;
      overflow: hidden;
      visibility: hidden;
  }
  .container {
      display: block;
  }
  ```

4. clear属性

  `<br style="clear:both" /> <!-- So dirty! -->`