//--------------- Wtrite XML exmaple 1 -------------------
```cs
var sts = new XmlWriterSettings()
{
    Indent = true,
};
using XmlWriter writer = XmlWriter.Create("test1.xml", sts);
writer.WriteStartDocument();
writer.WriteStartElement("value");
writer.WriteValue(123456789);
writer.WriteEndElement();
writer.WriteEndDocument();
Console.WriteLine("XML document created");
```


//--------------- Wtrite XML exmaple 2 -------------------
```cs
var sts = new XmlWriterSettings()
{
    Indent = true,
};
using var writer = XmlWriter.Create("books.xml", sts);
writer.WriteStartDocument();
writer.WriteStartElement("bookstore");

    writer.WriteStartElement("book");
        writer.WriteAttributeString("genre", "Science Fiction");

    writer.WriteStartElement("title");
        writer.WriteString("Dune");
    writer.WriteEndElement();

    writer.WriteStartElement("author");
        writer.WriteString("Frank Herbert");
    writer.WriteEndElement();

    writer.WriteStartElement("price");
        writer.WriteString("8.99");
    writer.WriteEndElement();

    writer.WriteEndElement(); // end of book

writer.WriteStartElement("book");
writer.WriteAttributeString("genre", "Novel");

writer.WriteStartElement("title");
    writer.WriteString("Old Goriot");
writer.WriteEndElement();

writer.WriteStartElement("author");
    writer.WriteString("Honoré de Balzac");
writer.WriteEndElement();

writer.WriteStartElement("price");
    writer.WriteString("9.0");
writer.WriteEndElement();

writer.WriteEndElement(); // end of book

writer.WriteEndDocument();

Console.WriteLine("XML document created");

```
