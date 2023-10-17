```cs
            var xmlFile = "XmlData.txt"; //change to your own file

            var doc = new XmlDocument();
            doc.Load(xmlFile);

            XmlElement root = doc.DocumentElement;
            XmlNode userNode = root?.LastChild;

            if (userNode != null)
            {
                root.RemoveChild(userNode);
            }

            var xmlFile2 = "XmlData2.txt"; // change to your own file // keep same file name to overwrite or enter new file name to save new document

            doc.Save(xmlFile2);
        }
```
