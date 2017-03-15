---
title: "binary_delegate_noreturn (STL/CLR) | Microsoft Docs"
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
  - "cliext::binary_delegate_noreturn"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "binary_delegate_noreturn (fonction) (STL/CLR)"
ms.assetid: 055c7e9d-e5c3-48fe-9327-3f6316e8a51e
caps.latest.revision: 8
caps.handback.revision: 6
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# binary_delegate_noreturn (STL/CLR)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

La classe genereic décrit un délégué à deux arguments qui retourne `void`.  Vous l'utilisez pour spécifier un délégué en ce qui concerne ses arguments.  
  
## Syntaxe  
  
```  
generic<typename Arg1,  
    typename Arg2>  
    delegate void binary_delegate(Arg1, Arg2);  
```  
  
#### Paramètres  
 Arg1  
 Type du premier argument délégué.  
  
 Arg2  
 Le type du second argument.  
  
## Notes  
 Le délégué genereic décrit une fonction de deux arguments qui retourne `void`.  
  
 Notez que pour :  
  
 `binary_delegate_noreturn<int, int> Fun1;`  
  
 `binary_delegate_noreturn<int, int> Fun2;`  
  
 les types `Fun1` et `Fun2` sont synonymes, tandis que pour:  
  
 `delegate void Fun1(int, int);`  
  
 `delegate void Fun2(int, int);`  
  
 ils ne sont pas du même type.  
  
## Exemple  
  
```  
// cliext_binary_delegate_noreturn.cpp   
// compile with: /clr   
#include <cliext/functional>   
  
void key_compare(wchar_t left, wchar_t right)   
    {   
    System::Console::WriteLine("compare({0}, {1}) = {2}",   
        left, right, left < right);   
    }   
  
typedef cliext::binary_delegate_noreturn<wchar_t, wchar_t> Mydelegate;   
int main()   
    {   
    Mydelegate^ kcomp = gcnew Mydelegate(&key_compare);   
  
    kcomp(L'a', L'a');   
    kcomp(L'a', L'b');   
    kcomp(L'b', L'a');   
    System::Console::WriteLine();   
    return (0);   
    }  
  
```  
  
  **comparez \(a, a\) \= Faux**  
**comparez \(a, b\) \= Vrai**  
**comparez \(b, a\) \= Faux**   
## Configuration requise  
 **En\-tête :** \<cliext\/functional\>  
  
 **Espace de nom :** cliext  
  
## Voir aussi  
 [binary\_delegate](../dotnet/binary-delegate-stl-clr.md)   
 [unary\_delegate](../dotnet/unary-delegate-stl-clr.md)   
 [unary\_delegate\_noreturn](../dotnet/unary-delegate-noreturn-stl-clr.md)