---
title: "Attribute Programming FAQ | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "attributed programming"
  - "attributes [C++], frequently asked questions"
  - "FAQs (frequently asked questions), attributed programming [C++]"
ms.assetid: a1b8349f-7f51-43c4-95ea-4edb6e5f243f
caps.latest.revision: 8
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 8
---
# Attribute Programming FAQ
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Cette rubrique fournit à des questions suivant :  
  
-   [Qu'est\-ce qu'un HRESULT ?](#vcconattributeprogrammmingfaqanchor1)  
  
-   [Lorsque faire pour dois spécifier le nom de paramètre pour un attribut ?](#vcconattributeprogrammmingfaqanchor2)  
  
-   [Puis \-je utiliser des commentaires dans un bloc d'attributs ?](#vcconattributeprogrammmingfaqanchor3)  
  
-   [comment les attributs interagissent\-ils avec l'héritage ?](#vcconattributeprogrammmingfaqanchor4)  
  
-   [Comment puis \-je utiliser des attributs dans un projet ATL sans attributs ?](#vcconattributeprogrammmingfaqanchor5)  
  
-   [Comment puis \-je utiliser un fichier .idl dans un projet attribué ?](#vcconattributeprogrammmingfaqanchor6)  
  
-   [Puis \-je modifier le code qui est injecté par un attribut ?](#vcconattributeprogrammmingfaqanchor7)  
  
-   [Comment puis \-je transférer déclare une interface avec attributs ?](#vcconattributeprogrammmingfaqhowcaniforwarddeclareanattributedinterface)  
  
-   [Puis \-je utiliser des attributs d'une classe dérivée d'une classe qui utilise également des attributs ?](#vcconcaniuseattributesonclassderivedfromclassthatalsousesattributesanchor)  
  
##  <a name="vcconattributeprogrammmingfaqanchor1"></a> Qu'est\-ce qu'un HRESULT ?  
 `HRESULT` est un type de données simple qui est souvent utilisé comme valeur de retour par des attributs et ATL en général.  le tableau suivant décrit les différentes valeurs.  Plus de valeurs figurent dans le fichier d'en\-tête winerror.h.  
  
|Nom|Description|Valeur|  
|---------|-----------------|------------|  
|S\_OK|opération réussie|0x00000000|  
|E\_UNEXPECTED|Défaillance inattendue|0x8000FFFF|  
|E\_NOTIMPL|non implémenté|0x80004001|  
|E\_OUTOFMEMORY|Pour allouer de la mémoire nécessaire|0x8007000E|  
|E\_INVALIDARG|un ou plusieurs arguments sont valides|0x80070057|  
|E\_NOINTERFACE|Aucun ces interface prise en charge|0x80004002|  
|E\_POINTER|Pointeur non valide|0x80004003|  
|E\_HANDLE|handle valide|0x80070006|  
|E\_ABORT|opération interrompue|0x80004004|  
|E\_FAIL|échec non spécifié|0x80004005|  
|E\_ACCESSDENIED|erreur générale d'accès refusé|0x80070005|  
  
##  <a name="vcconattributeprogrammmingfaqanchor2"></a> Lorsque faire pour dois spécifier le nom de paramètre pour un attribut ?  
 Dans la plupart des cas, si l'attribut possède un paramètre unique, ce paramètre est nommé.  Ce nom n'est pas requis en insérant l'attribut dans votre code.  par exemple, l'utilisation suivante de l'attribut d' [aggregatable](../windows/aggregatable.md) :  
  
```  
[coclass, aggregatable(value=allowed)]  
class CMyClass  
{  
// The class declaration  
};  
```  
  
 est exactement le même que :  
  
```  
[coclass, aggregatable(allowed)]  
class CMyClass  
{  
// The class declaration  
};  
```  
  
 Toutefois, les attributs suivants ont unique, paramètres sans nom :  
  
||||  
|-|-|-|  
|[call\_as](../windows/call-as.md)|[case](../windows/case-cpp.md)|[cpp\_quote](../windows/cpp-quote.md)|  
|[par défaut](../windows/default-cpp.md)|[defaultvalue](../windows/defaultvalue.md)|[defaultvtable](../windows/defaultvtable.md)|  
|[emitidl](../windows/emitidl.md)|[entrée](../windows/entry.md)|[first\_is](../windows/first-is.md)|  
|[helpcontext](../windows/helpcontext.md)|[helpfile](../windows/helpfile.md)|[helpstring](../windows/helpstring.md)|  
|[helpstringcontext](../windows/helpstringcontext.md)|[helpstringdll](../windows/helpstringdll.md)|[id](../windows/id.md)|  
|[iid\_is](../windows/iid-is.md)|[import](../windows/import.md)|[importlib](../windows/importlib.md)|  
|[incluez](../windows/include-cpp.md)|[includelib](../windows/includelib-cpp.md)|[last\_is](../windows/last-is.md)|  
|[length\_is](../windows/length-is.md)|[max\_is](../windows/max-is.md)|[no\_injected\_text](../windows/no-injected-text.md)|  
|[pointer\_default](../windows/pointer-default.md)|[pragma](../windows/pragma.md)|[restricted](../windows/restricted.md)|  
|[size\_is](../windows/size-is.md)|[source](../windows/source-cpp.md)|[switch\_is](../windows/switch-is.md)|  
|[switch\_type](../windows/switch-type.md)|[transmit\_as](../windows/transmit-as.md)|[wire\_marshal](../windows/wire-marshal.md)|  
  
##  <a name="vcconattributeprogrammmingfaqanchor3"></a> Puis \-je utiliser des commentaires dans un bloc d'attributs ?  
 Vous pouvez utiliser des commentaires sur une seule ligne et sur plusieurs lignes dans un bloc d'attributs.  Toutefois, vous ne pouvez pas utiliser l'un ou l'autre de style de commentaire entre parenthèses maintenant les paramètres dans un attribut.  
  
 Il permet les éléments suivants :  
  
```  
[ coclass,  
   progid("MyClass.CMyClass.1"), /* Multiple-line  
                                       comment */  
   threading("both") // Single-line comment  
]  
```  
  
 Ce qui suit est interdit :  
  
```  
[ coclass,  
   progid("MyClass.CMyClass.1" /* Multiple-line comment */ ),  
   threading("both" // Single-line comment)  
]  
```  
  
##  <a name="vcconattributeprogrammmingfaqanchor4"></a> comment les attributs interagissent\-ils avec l'héritage ?  
 Vous pouvez hériter des classes attribuées et non attribuées d'autres classes, qui peuvent être réaffectées ou pas.  Le résultat de la dérivation d'une classe avec attributs est le même que dérivant de cette classe après que le fournisseur d'attribut a transformé son code.  Les attributs ne sont pas transmis aux classes dérivées via l'héritage C\+\+.  Le code de transformations du fournisseur d'attribut que à proximité de ses attributs.  
  
##  <a name="vcconattributeprogrammmingfaqanchor5"></a> Comment puis \-je utiliser des attributs dans un projet ATL sans attributs ?  
 Vous pouvez avoir un projet ATL sans attributs, qui comporte un fichier .idl, et vous pouvez démarrer des objets avec attributs d'addition.  Dans ce cas, utilisez l'Assistant pour ajouter une classe pour fournir le code.  
  
##  <a name="vcconattributeprogrammmingfaqanchor6"></a> Comment puis \-je utiliser un fichier .idl dans un projet attribué ?  
 Vous pouvez utiliser un fichier .idl à utiliser dans votre projet attribué par ATL.  Dans ce cas, vous pouvez utiliser l'attribut d' [importidl](../windows/importidl.md) , compilez le fichier .idl à un fichier .h \(consultez [Pages de propriétés MIDL](../ide/midl-property-pages.md) dans la boîte de dialogue pages de propriétés du projet\), puis inclure le fichier .h dans votre projet.  
  
##  <a name="vcconattributeprogrammmingfaqanchor7"></a> Puis \-je modifier le code qui est injecté par un attribut ?  
 Certains attributs injectent un code dans votre projet.  Vous pouvez consulter le code injecté à l'aide de l'option du compilateur de [\/Fx](../build/reference/fx-merge-injected-code.md) .  Il est également possible de copier le code dans le fichier injecté et de le coller dans votre code source.  Cela vous permet de modifier le comportement de l'attribut.  Toutefois, vous devrez peut\-être modifier d'autres parties de votre code également.  
  
 l'exemple suivant est le résultat de code injecté par copie dans un fichier de code source :  
  
```  
// attr_injected.cpp  
// compile with: comsupp.lib  
#define _ATL_ATTRIBUTES 1  
#include <atlbase.h>  
#include <atlcom.h>  
  
[ module(name="MyLibrary") ];  
  
// ITestTest  
[   
   object,  
   uuid("DADECE00-0FD2-46F1-BFD3-6A0579CA1BC4"),  
   dual,  
   helpstring("ITestTest Interface"),  
   pointer_default(unique)  
]  
  
__interface ITestTest : IDispatch {  
   [id(1), helpstring("method DoTest")]   
   HRESULT DoTest([in] BSTR str);  
};  
  
// _ITestTestEvents  
[  
   uuid("12753B9F-DEF4-49b0-9D52-A79C371F2909"),  
   dispinterface,  
   helpstring("_ITestTestEvents Interface")  
]  
  
__interface _ITestTestEvents {  
   [id(1), helpstring("method BeforeChange")] HRESULT BeforeChange([in] BSTR str, [in,out] VARIANT_BOOL* bCancel);  
};  
  
// CTestTest  
[  
   coclass,  
   threading(apartment),  
   vi_progid("TestATL1.TestTest"),  
   progid("TestATL1.TestTest.1"),  
   version(1.0),  
   uuid("D9632007-14FA-4679-9E1C-28C9A949E784"),  
   // this line would be commented out from original file  
   // event_source("com"),  
   // this line would be added to support injected code  
   source(_ITestTestEvents),  
   helpstring("TestTest Class")  
]  
  
class ATL_NO_VTABLE CTestTest : public ITestTest,  
// the following base classes support added injected code  
public IConnectionPointContainerImpl<CTestTest>,  
public IConnectionPointImpl<CTestTest, &__uuidof(::_ITestTestEvents), CComDynamicUnkArray>  
{  
public:  
   CTestTest() {  
   }  
   // this line would be commented out from original file  
   // __event __interface _ITestTestEvents;  
   DECLARE_PROTECT_FINAL_CONSTRUCT()  
   HRESULT FinalConstruct() {  
      return S_OK;  
   }  
  
void FinalRelease() {}  
  
public:  
   CComBSTR m_value;  
   STDMETHOD(DoTest)(BSTR str) {  
      VARIANT_BOOL bCancel = FALSE;  
      BeforeChange(str,&bCancel);  
      if (bCancel) {  
          return Error("Error : Someone don't want us to change the value");  
      }  
  
     m_value =str;  
     return S_OK;  
    }  
// the following was copied in from the injected code.  
HRESULT BeforeChange(::BSTR i1,::VARIANT_BOOL* i2) {  
   HRESULT hr = S_OK;  
   IConnectionPointImpl<CTestTest, &__uuidof(_ITestTestEvents), CComDynamicUnkArray>* p = this;  
   VARIANT rgvars[2];  
   Lock();  
   IUnknown** pp = p->m_vec.begin();  
   Unlock();  
   while (pp < p->m_vec.end()) {  
      if (*pp != NULL) {  
         IDispatch* pDispatch = (IDispatch*) *pp;  
         ::VariantInit(&rgvars[1]);  
         rgvars[1].vt = VT_BSTR;  
         V_BSTR(&rgvars[1])= (BSTR) i1;  
         ::VariantInit(&rgvars[0]);  
         rgvars[0].vt = (VT_BOOL | VT_BYREF);  
         V_BOOLREF(&rgvars[0])= (VARIANT_BOOL*) i2;  
         DISPPARAMS disp = { rgvars, NULL, 2, 0 };  
         VARIANT ret_val;  
         hr = __ComInvokeEventHandler(pDispatch, 1, 1, &disp, &ret_val);  
         if (FAILED(hr))  
            break;  
      }  
      pp++;  
   }  
   return hr;  
}  
  
BEGIN_CONNECTION_POINT_MAP(CTestTest)  
CONNECTION_POINT_ENTRY(__uuidof(::_ITestTestEvents))  
END_CONNECTION_POINT_MAP()  
// end added code section  
  
// _ITestCtrlEvents Methods  
public:  
};  
  
int main() {}  
```  
  
##  <a name="vcconattributeprogrammmingfaqhowcaniforwarddeclareanattributedinterface"></a> Comment puis \-je transférer déclare une interface avec attributs ?  
 Si vous souhaitez effectuer une déclaration anticipée d'une interface avec attributs, vous devez appliquer les mêmes attributs à la déclaration anticipée que vous appliquez à la déclaration réelle de l'interface.  Vous devez également appliquer l'attribut importer à votre déclaration anticipée.  
  
##  <a name="vcconcaniuseattributesonclassderivedfromclassthatalsousesattributesanchor"></a> Puis \-je utiliser des attributs d'une classe dérivée d'une classe qui utilise également des attributs ?  
 Non, à l'aide de les attributs d'une classe dérivée d'une classe qui utilise également des attributs n'est pas pris en charge.  
  
## Voir aussi  
 [Concepts](../windows/attributed-programming-concepts.md)