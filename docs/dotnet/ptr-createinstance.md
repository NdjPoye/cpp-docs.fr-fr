---
title: "ptr::CreateInstance | Microsoft Docs"
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
  - "ptr.CreateInstance"
  - "msclr::com::ptr::CreateInstance"
  - "msclr.com.ptr.CreateInstance"
  - "ptr::CreateInstance"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "ptr::CreateInstance"
ms.assetid: 9e8e4c4c-1651-4839-8829-5857d74470fe
caps.latest.revision: 11
caps.handback.revision: 11
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# ptr::CreateInstance
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Crée une instance d'un objet COM avec `com::ptr`.  
  
## Syntaxe  
  
```  
void CreateInstance(  
   System::String ^ progid,  
   LPUNKNOWN pouter,  
   DWORD cls_context  
);  
void CreateInstance(  
   System::String ^ progid,  
   LPUNKNOWN pouter  
);  
void CreateInstance(  
   System::String ^ progid  
);  
void CreateInstance(  
   const wchar_t * progid,  
   LPUNKNOWN pouter,  
   DWORD cls_context  
);  
void CreateInstance(  
   const wchar_t * progid,  
   LPUNKNOWN pouter  
);  
void CreateInstance(  
   const wchar_t * progid  
);  
void CreateInstance(  
   REFCLSID rclsid,  
   LPUNKNOWN pouter,  
   DWORD cls_context  
);  
void CreateInstance(  
   REFCLSID rclsid,  
   LPUNKNOWN pouter  
);  
void CreateInstance(  
   REFCLSID rclsid  
);  
```  
  
#### Paramètres  
 `progid`  
 Chaîne `ProgID`.  
  
 `pouter`  
 Pointeur à l'aide de l'interface IUnknown de l'objet global \(l'IUnknown contrôle\).  En l'absence de `pouter` , `NULL` est utilisé.  
  
 `cls_context`  
 Contexte dans lequel le code qui gère l'objet créé récemment s'exécutera.  Les valeurs prises de l'énumération de `CLSCTX`.  Si `cls_context` n'est pas spécifié, la valeur CLSCTX\_ALL is used.  
  
 `rclsid`  
 `CLSID` Ce CLSID est associé aux données et au code utilisé pour créer l'objet.  
  
## Exceptions  
 Si `com::ptr` possède déjà une référence à un objet COM, `CreateInstance` lève <xref:System.InvalidOperationException>.  
  
 Appels de cette fonction `CoCreateInstance` et utilise <xref:System.Runtime.InteropServices.Marshal.ThrowExceptionForHR%2A> pour convertir une erreur `HRESULT` à une exception appropriée.  
  
## Notes  
 Utilise `CoCreateInstance` d'`CreateInstance` pour créer une nouvelle instance de l'objet, identifiée d'un progid ou du CLSID.  Le `com::ptr` référence l'objet créé récemment et libèrera automatiquement toutes les références détenues lors de la destruction.  
  
## Exemple  
 Cet exemple implémente une classe CLR qui utilise `com::ptr` pour encapsuler son objet de `IXMLDOMDocument` de membre privée.  Les constructeurs de fichiers utilisent des deux formes de `CreateInstance` pour créer l'objet document d'un progid ou du CLSID plus un CLSCTX.  
  
```  
// comptr_createinstance.cpp  
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
   XmlDocument(REFCLSID clsid, DWORD clsctx) {  
      m_ptrDoc.CreateInstance(clsid, NULL, clsctx);  
   }  
  
   // note that the destructor will call the com::ptr destructor  
   // and automatically release the reference to the COM object  
  
private:  
   com::ptr<IXMLDOMDocument> m_ptrDoc;  
};  
  
// use the ref class to handle an XML DOM Document object  
int main() {  
   try {  
      // create the class from a progid string  
      XmlDocument doc1("Msxml2.DOMDocument.3.0");  
  
      // or from a clsid with specific CLSCTX  
      XmlDocument doc2(CLSID_DOMDocument30, CLSCTX_INPROC_SERVER);  
   }  
   catch (Exception^ e) {  
      Console::WriteLine(e);     
   }  
}  
```  
  
## Configuration requise  
 msclr \<de**Fichier d'en\-tête** \\COM\\ptr.h\>  
  
 **Espace de noms** msclr::com  
  
## Voir aussi  
 [ptr, membres](../dotnet/ptr-members.md)