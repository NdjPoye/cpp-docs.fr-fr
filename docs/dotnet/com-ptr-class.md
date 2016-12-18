---
title: "com::ptr, classe | Microsoft Docs"
ms.custom: ""
ms.date: "12/05/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "com::ptr"
  - "msclr::com::ptr"
  - "msclr.com.ptr"
  - "com.ptr"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "ptr (classe)"
ms.assetid: 0144d0e4-919c-45f9-a3f8-fbc9edba32bf
caps.latest.revision: 10
caps.handback.revision: 8
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# com::ptr, classe
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Un wrapper d'un objet COM qui peut être utilisé en tant que membre d'une classe CLR.  Le wrapper automatise également la gestion de la durée de vie de l'objet COM, libérant toutes les références détenues sur l'objet lorsque son destructeur est appelé.  Analogue à [CComPtr Class](../atl/reference/ccomptr-class.md).  
  
## Syntaxe  
  
```  
template<class _interface_type>  
ref class ptr;  
```  
  
#### Paramètres  
 `_interface_type`  
 interface COM.  
  
## Notes  
 Un `com::ptr` peut également être utilisé comme une variable de fonction locale pour simplifier différentes tâches COM et automatiser la gestion de la durée de vie.  
  
 Un `com::ptr` ne peut pas être utilisé directement comme un paramètre de fonction ; utilisez [Tracking Reference Operator](../windows/tracking-reference-operator-cpp-component-extensions.md) ou [Handle sur l'opérateur Object \(^\)](../windows/handle-to-object-operator-hat-cpp-component-extensions.md) à la place.  
  
 Un `com::ptr` ne peut plus être directement renvoyé depuis fonction ; utilisez un descripteur à la place.  
  
## Exemple  
 Cet exemple implémente une classe CLR qui utilise `com::ptr` pour encapsuler son objet membre privé `IXMLDOMDocument`.  Appeler les méthodes publiques de la classe amène des appels à l'objet `IXMLDOMDocument` contenu.  L'exemple crée une instance d'un document XML, la remplit avec un certain XML simple ; il effectue un parcours simplifié des nœuds dans l'arborescence analysée du document pour imprimer le XML sur la console.  
  
```  
// comptr.cpp  
// compile with: /clr /link msxml2.lib  
#include <msxml2.h>  
#include <msclr\com\ptr.h>  
  
#import <msxml3.dll> raw_interfaces_only  
  
using namespace System;  
using namespace System::Runtime::InteropServices;  
using namespace msclr;  
  
// a ref class that uses a com::ptr to contain an   
// IXMLDOMDocument object  
ref class XmlDocument {  
public:  
   // construct the internal com::ptr with a null interface  
   // and use CreateInstance to fill it  
   XmlDocument(String^ progid) {  
      m_ptrDoc.CreateInstance(progid);     
   }  
  
   void LoadXml(String^ xml) {  
      pin_ptr<const wchar_t> pinnedXml = PtrToStringChars(xml);  
      BSTR bstr = NULL;  
  
      try {  
         // load some XML into the document  
         bstr = ::SysAllocString(pinnedXml);  
         if (NULL == bstr) {  
            throw gcnew OutOfMemoryException;  
         }  
         VARIANT_BOOL bIsSuccessful = false;  
         // use operator -> to call IXMODOMDocument member function  
         Marshal::ThrowExceptionForHR(m_ptrDoc->loadXML(bstr, &bIsSuccessful));  
      }  
      finally {  
         ::SysFreeString(bstr);  
      }  
   }  
  
   // simplified function to write just the first xml node to the console  
   void WriteXml() {  
      IXMLDOMNode* pNode = NULL;  
  
      try {  
         // the first child of the document is the first real xml node  
         Marshal::ThrowExceptionForHR(m_ptrDoc->get_firstChild(&pNode));  
         if (NULL != pNode) {  
            WriteNode(pNode);  
         }  
      }  
      finally {  
         if (NULL != pNode) {  
            pNode->Release();  
         }  
      }  
   }  
  
   // note that the destructor will call the com::ptr destructor  
   // and automatically release the reference to the COM object  
  
private:  
   // simplified function that only writes the node  
   void WriteNode(IXMLDOMNode* pNode) {  
      BSTR bstr = NULL;  
  
      try {  
         // write out the name and text properties  
         Marshal::ThrowExceptionForHR(pNode->get_nodeName(&bstr));  
         String^ strName = gcnew String(bstr);  
         Console::Write("<{0}>", strName);  
         ::SysFreeString(bstr);  
         bstr = NULL;  
  
         Marshal::ThrowExceptionForHR(pNode->get_text(&bstr));  
         Console::Write(gcnew String(bstr));  
         ::SysFreeString(bstr);  
         bstr = NULL;  
  
         Console::WriteLine("</{0}>", strName);  
      }  
      finally {  
         ::SysFreeString(bstr);  
      }  
   }  
  
   com::ptr<IXMLDOMDocument> m_ptrDoc;  
};  
  
// use the ref class to handle an XML DOM Document object  
int main() {  
   try {  
      // create the class from a progid string  
      XmlDocument doc("Msxml2.DOMDocument.3.0");  
  
      // stream some xml into the document  
      doc.LoadXml("<word>persnickety</word>");  
  
      // write the document to the console  
      doc.WriteXml();  
   }  
   catch (Exception^ e) {  
      Console::WriteLine(e);     
   }  
}  
```  
  
  **\<mot\>persnickety\<\/mot\>**   
## Configuration requise  
 **Fichier d'en\-tête** \<msclr\\com\\ptr.h\>  
  
 **Espace de nom** msclr::com  
  
## Voir aussi  
 [Bibliothèque de prise en charge C\+\+](../dotnet/cpp-support-library.md)   
 [ptr, membres](../dotnet/ptr-members.md)