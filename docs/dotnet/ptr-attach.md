---
title: "ptr::Attach | Microsoft Docs"
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
  - "msclr::com::ptr::Attach"
  - "ptr::Attach"
  - "ptr.Attach"
  - "msclr.com.ptr.Attach"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "Attach (méthode)"
ms.assetid: 81d930de-cb2a-4c30-9bd6-94d65942c47a
caps.latest.revision: 8
caps.handback.revision: 8
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# ptr::Attach
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Joint un objet COM à `com::ptr`.  
  
## Syntaxe  
  
```  
void Attach(  
   _interface_type * _right  
);  
```  
  
#### Paramètres  
 `_right`  
 Le pointeur d'interface COM à joindre.  
  
## Exceptions  
 Si `com::ptr` possède déjà une référence à un objet COM, `Attach` lève <xref:System.InvalidOperationException>.  
  
## Notes  
 Un appel à `Attach` référence l'objet COM mais ne libère pas la référence de l'appelant à celui\-ci.  
  
 Passer `NULL` à `Attach` entraîne qu'aucune action n'est effectuée.  
  
## Exemple  
 Cet exemple implémente une classe CLR qui utilise un `com::ptr` pour encapsuler son objet membre privé `IXMLDOMDocument`.  La fonction membre `ReplaceDocument` appelle `Release` d'abord pour tout objet précédemment possédé puis appelle ensuite `Attach` pour joindre un nouvel objet document.  
  
```  
// comptr_attach.cpp  
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
  
   // replace currently held COM object with another one  
   void ReplaceDocument(IXMLDOMDocument* pDoc) {  
      // release current document object  
      m_ptrDoc.Release();  
      // attach the new document object  
      m_ptrDoc.Attach(pDoc);  
   }  
  
   // note that the destructor will call the com::ptr destructor  
   // and automatically release the reference to the COM object  
  
private:  
   com::ptr<IXMLDOMDocument> m_ptrDoc;  
};  
  
// unmanaged function that creates a raw XML DOM Document object  
IXMLDOMDocument* CreateDocument() {  
   IXMLDOMDocument* pDoc = NULL;  
   Marshal::ThrowExceptionForHR(CoCreateInstance(CLSID_DOMDocument30, NULL,  
      CLSCTX_INPROC_SERVER, IID_IXMLDOMDocument, (void**)&pDoc));  
   return pDoc;  
}  
  
// use the ref class to handle an XML DOM Document object  
int main() {  
   IXMLDOMDocument* pDoc = NULL;  
  
   try {  
      // create the class from a progid string  
      XmlDocument doc("Msxml2.DOMDocument.3.0");  
  
      // get another document object from unmanaged function and  
      // store it in place of the one held by our ref class  
      pDoc = CreateDocument();  
      doc.ReplaceDocument(pDoc);  
      // no further need for raw object reference  
      pDoc->Release();  
      pDoc = NULL;  
   }  
   catch (Exception^ e) {  
      Console::WriteLine(e);     
   }  
   finally {  
      if (NULL != pDoc) {  
         pDoc->Release();  
      }  
   }  
}  
```  
  
## Configuration requise  
 **Fichier d'en\-tête** \<msclr\\com\\ptr.h\>  
  
 **Espace de nommage** msclr::com  
  
## Voir aussi  
 [ptr, membres](../dotnet/ptr-members.md)   
 [ptr::operator\=](../dotnet/ptr-operator-assign.md)   
 [ptr::Release](../dotnet/ptr-release.md)