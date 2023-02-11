using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
using System.Threading.Tasks;
using Newtonsoft.Json;

namespace JSONToObject
{
    internal class Program
    {
        static void Main(string[] args)
        {
            string countryJsonStr = @"{
               Name:""India"",
               Population:138,
               Cities:[""Mumbai"",""Delhi""]

           }";

            var country =JsonConvert.DeserializeObject<Country>(countryJsonStr);
            Console.WriteLine(country.Name);
            Console.WriteLine("Cities: " + string.Join(",", country.Cities));
        }
    }
    public class Country
    {
        public string Name { get; set; }
        public int Population { get; set; }
        public List<string>Cities { get; set; }
    }
}
