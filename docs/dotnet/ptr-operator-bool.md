---
title: "ptr::operator (bool) | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "ptr::operator bool"
  - "ptr.operator bool"
  - "operator bool"
  - "msclr::com::ptr::operator bool"
  - "msclr.com.ptr.operator bool"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "ptr::operator (bool)"
ms.assetid: 31123377-6ecd-4cef-9b75-3db3996fbcd1
caps.latest.revision: 10
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 8
---
# ptr::operator (bool)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Opérateur pour l'utilisation de `com::ptr` dans une expression conditionnelle.  
  
## Syntaxe  
  
```  
operator bool();  
```  
  
## Valeur de retour  
 `true` si l'objet possédé COM est valide; sinon `false`.  
  
## Notes  
 L'objet COM possédé n'est pas valide s'il n'est pas `nullptr`.  
  
 L'opérateur convertit en fait à `_detail_class::_safe_bool` qui est plus sûr que `bool` car il ne peut pas être converti en un type intégral.  
  
## Exemple  
 Cet exemple implémente une classe CLR qui utilise un `com::ptr` pour encapsuler son objet membre privé `IXMLDOMDocument`.  La fonction membre d' `CreateInstance` utilise `operator bool` après avoir créé le nouvel objet de document pour déterminer si il est valide et l'écrit dans la console si tel est le cas.  
  
```  
// comptr_op_bool.cpp  
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
         if (m_ptrDoc) { // uses operator bool  
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
 [ptr::operator\!](../dotnet/ptr-operator-logical-not.md)