---
title: "Programatically Generate documents with Enterprise Architect "
read_time: true
categories:  
  - architecture
tags:
  - enterprise architect
  - documents generation
  - sparx
  
---

Enterprise Architect is a tool for architecture modelling at base, but can be used for much more.

What the tool can improve is the way to generate documents based on the AutomationInterface.

There are two ways to generate documents in EA Sparx:
1)  DocumentGenerator
{% highlight  %}
  function createDocument( docName, docPath  )
  {
      var Gentor as EA.DocumentGenerator;
      Gentor = Repository.CreateDocumentGenerator();
      Gentor.NewDocument("Glossary");    
	    Gentor.InsertText( "Hello World" +"\n","Heading 1");		
	    return Gentor; 
  }

  createDocument ("yourDocName", "yourDocPath");
{% endhighlight %}

2)  Virtual Document 

This option is based on this link from <a href="https://bellekens.com/2015/11/12/tutorial-generate-complex-documents-from-enterprise-architect-with-a-two-step-semi-automated-approach/" target="_blank"> Bellekens </a>
but adapted.
The code below calls RunReport that runs the F8 (or generate documents) document generation option.

  !INC Local Scripts.EAConstants-JScript

  function main()
  {	
	  Session.Output("Hello World");
	
	  var prj = Repository.GetProjectInterface();
	  prj.RunReport("{GUID}", "test","C:\\diagram_export\\3.rtf");
	
	  Session.Output("Bye World");
  }

  main();



---
