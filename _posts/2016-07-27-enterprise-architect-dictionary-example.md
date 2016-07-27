```ruby
/*
 * Script Name: A simple dictionary example
 * Purpose: Showcasing the dictionary object in Windows Script
 * Date:  21.07.2016
 * Modified: 21.07.2016
 */


function DictionaryExample()
{
	// Show the script output window
	Repository.EnsureOutputVisible( "Script" );

	Session.Output( "JScript DICTIONARY EXAMPLE" );
	Session.Output( "=======================================" );
	
	var d, a, keyword = "C", exists, items ;
	d = new ActiveXObject("Scripting.Dictionary");
	d.Add("a", "Athens");
	d.Add("b", "Belgrade");
	d.Add("c", "Cairo");

	a = ItemProperty (d, keyword );
	Session.Output("The result for " + keyword + " is : " + a);		
	
	var items = ItemsDemo (d);
	Session.Output(items);
	
	var exists = keyExists (d, keyword);
	Session.Output(exists);
	var contextType = Repository.GetContextItemType();
	
	Session.Output( "The dictionary has " + d.Count + " item(s) in it." );	
	Session.Output( "Done!" );		
}

// sets a key in the dictionary
//https://msdn.microsoft.com/en-us/library/1ex01tte(v=vs.84).aspx
function ChangeKey(oldkey, newkey)
{
   var s;
   d.Key("c") = "Ca";
   s = "Key " + oldkey + " changed to " + newkey;
   return(s);
}

//search dictionary by key
// it is case sensitive
function ItemProperty (d, keyword)
{
	var a;
	
	a = d.Item(keyword);
   return(a);
}

function ItemsDemo(d)
{
   var a, d, i, s;                  // Create some variables.
   
   a = (new VBArray(d.Items())).toArray();   // Get the items.
   s = "";
   for (i in a)                  // Iterate the dictionary.
   {
      s += a[i] + "<br>";
   }
   return(s);                     // Return the results.
}

//it is not case sensitive
function keyExists(d, k)
{
    var s = "";
    
    if (d.Exists(k))
        s += "Specified key exists.";
    else 
        s += "Specified key does not exist.";
    return(s);
}


DictionaryExample();

```
