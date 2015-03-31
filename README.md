WTForms-Polyglot
================

WTForms companion library providing `PolyglotForm` for [polyglot HTML][1]
output.

Polyglot markup is a set of rules for how to write HTML.  A document that uses
polyglot markup is both a valid HTML5 document as well as a well-formed XML
document, that can be served with either a `text/html` or an
`application/xhtml+xml` MIME type.

This package provides the `PolyglotForm` class, which is built on top of
WTForms’ default `Form`.  When using `PolyglotForm`, fields will be rendered
with polyglot markup.  For example, given the following form:

    from wtf_polyglot import PolyglotForm
    from wtforms import BooleanField

    class MyForm(PolyglotForm):
        foo = BooleanField('foo', default=True)

Rendering `MyForm.foo` will result in the following XML-compliant output:

    <input checked="checked" id="foo" name="foo" type="checkbox" value="y" />

In contrast, using WTForms’ default `Form`, the output would be:

    <input checked id="foo" name="foo" type="checkbox" value="y">


[1]: http://www.w3.org/TR/html-polyglot/