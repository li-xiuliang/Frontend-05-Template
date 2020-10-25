&lt;Expresion&gt;::=
 
>&lt;AdditiveExpression&gt;&lt;EOF&gt;

&lt;AdditiveExpression&gt;::=

>&lt;MultiplicativeExpression&gt;

>|&lt;AdditiveExpression&gt;&lt;+&gt;&lt;MultiplicativeExpression&gt;

>|&lt;AdditiveExpression&gt;&lt;-&gt;&lt;MultiplicativeExpression&gt;

&lt;MultiplicativeExpression&gt;::=

>&lt;Number&gt;

>|&lt;MultiplicativeExpression&gt;&lt;*&gt;&lt;Number&gt;

>|&lt;MultiplicativeExpression&gt;&lt;/&gt;&lt;Number&gt;

匹配四则各个元素：
       regexp = /([0-9\.]+)|([ \t]+)|([\r\n]+)|(\*)|(\/)|(\+)|(\-)/g
            
从最高优先级 乘除表达式开始，逐级合并运算内容，最终形成一个结果。