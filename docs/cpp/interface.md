---
title: "__interface | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
f1_keywords: 
  - "__interface"
  - "__interface_cpp"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "__interface (mot clé) (C++)"
ms.assetid: ca5d400b-d6d8-4ba2-89af-73f67e5ec056
caps.latest.revision: 10
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 8
---
# __interface
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

**Section spécifique à Microsoft**  
  
 Une interface Visual C\+\+ peut être définie comme suit :  
  
-   Peut hériter de zéro ou plusieurs interfaces de base.  
  
-   Ne peut pas hériter d'une classe de base.  
  
-   Ne peut contenir que des méthodes publiques, virtuelles pures.  
  
-   Ne peut pas contenir de constructeurs, de destructeurs ou d'opérateurs.  
  
-   Ne peut pas contenir de méthodes statiques.  
  
-   Ne peut pas contenir de données membres ; les propriétés sont autorisées.  
  
## Syntaxe  
  
```  
  
modifier  
 __interface interface-name {interface-definition};  
```  
  
## Notes  
 Un objet C\+\+ [class](../cpp/class-cpp.md) ou [struct](../cpp/struct-cpp.md) peut être mis en œuvre avec ces règles, mais c'est `__interface` qui les applique.  
  
 Par exemple, voici un exemple de définition d'interface :  
  
```  
__interface IMyInterface {  
   HRESULT CommitX();  
   HRESULT get_X(BSTR* pbstrName);  
};  
```  
  
 Pour plus d'informations sur les interfaces managées, consultez [classe d'interface](../windows/interface-class-cpp-component-extensions.md).  
  
 Notez que vous n'êtes pas obligé d'indiquer explicitement que `CommitX` et `get_X` sont des fonctions virtuelles pures.  Une déclaration équivalente pour la première fonction se présenterait comme suit :  
  
```  
virtual HRESULT CommitX() = 0;  
```  
  
 `__interface` implique le modificateur [novtable](../cpp/novtable.md) `__declspec`.  
  
## Exemple  
 L'exemple suivant montre comment utiliser les propriétés déclarées dans une interface.  
  
```  
// deriv_interface.cpp  
#define _ATL_ATTRIBUTES 1  
#include <atlbase.h>  
#include <atlcom.h>  
#include <string.h>  
#include <comdef.h>  
#include <stdio.h>  
  
[module(name="test")];  
  
[ object, uuid("00000000-0000-0000-0000-000000000001"), library_block ]  
__interface IFace {  
   [ id(0) ] int int_data;  
   [ id(5) ] BSTR bstr_data;  
};  
  
[ coclass, uuid("00000000-0000-0000-0000-000000000002") ]  
class MyClass : public IFace {  
private:  
    int m_i;  
    BSTR m_bstr;   
  
public:  
    MyClass()  
    {  
        m_i = 0;  
        m_bstr = 0;  
    }  
  
    ~MyClass()  
    {  
        if (m_bstr)   
            ::SysFreeString(m_bstr);  
    }  
  
    int get_int_data()  
    {  
        return m_i;  
    }  
  
    void put_int_data(int _i)   
    {  
        m_i = _i;  
    }  
  
    BSTR get_bstr_data()  
    {   
        BSTR bstr = ::SysAllocString(m_bstr);  
        return bstr;   
    }  
  
    void put_bstr_data(BSTR bstr)   
    {   
        if (m_bstr)   
            ::SysFreeString(m_bstr);  
        m_bstr = ::SysAllocString(bstr);  
    }  
};  
  
int main()  
{  
    _bstr_t bstr("Testing");  
    CoInitialize(NULL);  
    CComObject<MyClass>* p;  
    CComObject<MyClass>::CreateInstance(&p);  
    p->int_data = 100;  
    printf_s("p->int_data = %d\n", p->int_data);                
    p->bstr_data = bstr;  
    printf_s("bstr_data = %S\n", p->bstr_data);  
}  
```  
  
  **p\-\>int\_data \= 100**  
**bstr\_data \= Testing**   
## FIN de la section spécifique à Microsoft  
  
## Voir aussi  
 [Mots clés C\+\+](../cpp/keywords-cpp.md)   
 [Interface Attributes](../windows/interface-attributes.md)