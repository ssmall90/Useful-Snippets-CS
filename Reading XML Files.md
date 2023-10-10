using System.Xml;

// example 1 

```cs
using var reader = XmlReader.Create("data.xml");
reader.MoveToContent();
var data = reader.ReadElementContentAsString();
Console.WriteLine(data);


// example 2

```cs
using var reader = XmlReader.Create("books.xml");
reader.ReadToFollowing("book");

do
{
    reader.MoveToFirstAttribute();
    Console.WriteLine($"genre: {reader.Value}");

    reader.ReadToFollowing("title");
    Console.WriteLine($"title: {reader.ReadElementContentAsString()}");

    reader.ReadToFollowing("author");
    Console.WriteLine($"author: {reader.ReadElementContentAsString()}");

    reader.ReadToFollowing("price");
    Console.WriteLine($"price: {reader.ReadElementContentAsString()}");

    Console.WriteLine("-------------------------------------------------");


}
while (reader.ReadToFollowing("book"));


//Example 3

```cs
Console.WriteLine("Products");
Console.WriteLine("----------------------");

using var reader = XmlReader.Create("products.xml");
reader.MoveToContent();

while (reader.Read())
{
    string result = reader.NodeType switch
    {
        XmlNodeType.Element when reader.Name == "product" => $"{reader.Name}\n",
        XmlNodeType.Element => $"{reader.Name}: ",
        XmlNodeType.Text => $"{reader.Value}\n",
        XmlNodeType.EndElement when reader.Name == "product" => "-------------------\n", _ => ""

    };
    Console.Write(result);
}
