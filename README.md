# Write.Txt.File
Write line to txt file simply

static void Main(string[] args)
        {
            string[] lines = { "1. Line", "2. Line", "3. Line", "4. Line" };

            System.IO.File.WriteAllLines(@"C:\testFolder\test.txt", lines);

            string text = "Lorem ipsum dolor sit amet, consectetur adipiscing elit." +
                "Morbi porttitor auctor sem ut lacinia." +
                "Duis molestie egestas orci ut semper." +
                "Sed nec magna in nulla pellentesque tristique." +
                "Nulla luctus sem aliquet tincidunt sodales. Quisque tincidunt viverra ante eu euismod." +
                "Donec sed massa lorem. Praesent in elit tristique, faucibus tellus eget, ornare neque." +
                "Donec consequat, lorem eget dapibus malesuada, urna justo bibendum enim, vitae aliquam est urna vitae eros. Sed bibendum laoreet tortor eget pretium.";

            System.IO.File.AppendAllText(@"C:\testFolder\test.txt", text);

            using (System.IO.StreamWriter txtFile = new System.IO.StreamWriter(@"C:\testFolder\test.txt"))
            {
                foreach (string line in lines)
                {
                    txtFile.WriteLine(line);
                }
                txtFile.WriteLine(text);
            }
            Console.ReadKey();
        }
