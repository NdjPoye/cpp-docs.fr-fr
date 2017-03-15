---
title: "ptr::operator! | Microsoft Docs"
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
  - "ptr::operator!"
  - "msclr::com::ptr::operator!"
  - "ptr.operator!"
  - "msclr.com.ptr.operator!"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "ptr::operator!"
ms.assetid: 7f4101dc-2045-42e7-abb1-6a30e17147f2
caps.latest.revision: 9
caps.handback.revision: 7
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# ptr::operator!
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Opérateur pour déterminer si l'objet COM propriétaire n'est pas valide.  
  
## Syntaxe  
  
```  
bool operator!();  
```  
  
## Valeur de retour  
 `true` si l'objet COM propriétaire est invalide ; `false` sinon.  
  
## Notes  
 L'objet COM propriétaire n'est pas valide s'il n'est pas `nullptr`.  
  
## Exemple  
 Cet exemple implémente une classe CLR qui utilise un `com::ptr` pour encapsuler son objet membre privé `IXMLDOMDocument`.  La fonction membre `CreateInstance` utilise `operator!` qui détermine si un objet document est déjà possédé, et crée uniquement une nouvelle instance si l'objet est invalide.  
  
```  
// comptr_op_not.cpp  
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
   void CreateInstance(String^ progid) {  
      if (!m_ptrDoc) {  
         m_ptrDoc.CreateInstance(progid);     
         if (m_ptrDoc) {  
            Console::WriteLine("DOM Document created.");  
         }  
      }  
   }  
  
   // note that the destructor will call the com::ptr destructor  
   // and automatically release the reference to the COM object  
  
private:  
   com::ptr<IXMLDOMDocument> m_ptrDoc;  
};  
  
// use the ref class to handle an XML DOM Document object  
int main() {  
   try {  
      XmlDocument doc;  
      // create the instance from a progid string  
      doc.CreateInstance("Msxml2.DOMDocument.3.0");  
   }  
   catch (Exception^ e) {  
      Console::WriteLine(e);     
   }  
}  
```  
  
  **Document DOM créé.**   
## Configuration requise  
 **Fichier d'en\-tête** \<msclr\\com\\ptr.h\>  
  
 **Espace de nommage** msclr::com  
  
## Voir aussi  
 [ptr, membres](../dotnet/ptr-members.md)   
 [ptr::operator \(bool\)](../dotnet/ptr-operator-bool.md)