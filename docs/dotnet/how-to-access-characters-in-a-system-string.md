---
title: "Comment&#160;: acc&#233;der aux caract&#232;res d&#39;un System::String | Microsoft Docs"
ms.custom: ""
ms.date: "12/05/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "get-started-article"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "caractères (C++), accéder dans System::String"
  - "exemples (C++), chaînes"
  - "chaînes (C++), accéder aux caractères"
ms.assetid: cfc89756-aef3-4988-907e-fb236dcb7087
caps.latest.revision: 11
caps.handback.revision: 9
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Comment&#160;: acc&#233;der aux caract&#232;res d&#39;un System::String
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Vous pouvez accéder aux caractères d'un objet <xref:System.String> pour les appels haute performance aux fonctions non managées qui prennent des chaînes `wchar_t*`.  Cette méthode génère un pointeur intérieur vers le premier caractère de l'objet <xref:System.String>.  Ce pointeur peut être manipulé directement ou être épinglé et passé à une fonction qui attend une chaîne `wchar_t` ordinaire.  
  
## Exemple  
 `PtrToStringChars` retourne un <xref:System.Char> qui est un pointeur intérieur \(également appelé `byref`\).  En tant que tel, il fait l'objet d'un garbage collection.  Vous ne devez pas épingler ce pointeur à moins que vous ayez l'intention de le passer à une fonction native.  
  
 Prenons le code suivant.  L'épinglage n'est pas nécessaire, car `ppchar` est un pointeur intérieur, et si le garbage collector déplace la chaîne qu'il désigne, il met également à jour `ppchar`.  Sans [pin\_ptr \(C\+\+\/CLI\)](../windows/pin-ptr-cpp-cli.md), le code fonctionne et ne présente pas le problème de performances potentiel provoqué par l'épinglage.  
  
 Si vous passez `ppchar`  à une fonction native, il doit s'agir d'un pointeur épingle ; le garbage collector n'est donc pas capable de mettre à jour tous les pointeurs sur le frame de pile non managé.  
  
```  
// PtrToStringChars.cpp  
// compile with: /clr  
#include<vcclr.h>  
using namespace System;  
  
int main() {  
   String ^ mystring = "abcdefg";  
  
   interior_ptr<const Char> ppchar = PtrToStringChars( mystring );  
  
   for ( ; *ppchar != L'\0'; ++ppchar )  
      Console::Write(*ppchar);  
}  
```  
  
  **abcdefg**   
## Exemple  
 Cet exemple montre où l'épinglage est nécessaire.  
  
```  
// PtrToStringChars_2.cpp  
// compile with: /clr  
#include <string.h>  
#include <vcclr.h>  
// using namespace System;  
  
size_t getlen(System::String ^ s) {  
   // Since this is an outside string, we want to be secure.  
   // To be secure, we need a maximum size.  
   size_t maxsize = 256;  
   // make sure it doesn't move during the unmanaged call  
   pin_ptr<const wchar_t> pinchars = PtrToStringChars(s);  
   return wcsnlen(pinchars, maxsize);  
};  
  
int main() {  
   System::Console::WriteLine(getlen("testing"));  
}  
```  
  
 **7**   
## Exemple  
 Un pointeur intérieur possède toutes les propriétés d'un pointeur C\+\+ natif.  Par exemple, vous pouvez l'utiliser pour parcourir une structure de données liées ainsi que pour procéder à des insertions et des suppressions qui utilisent un seul pointeur :  
  
```  
// PtrToStringChars_3.cpp  
// compile with: /clr /LD  
using namespace System;  
ref struct ListNode {  
   Int32 elem;   
   ListNode ^ Next;  
};  
  
void deleteNode( ListNode ^ list, Int32 e ) {   
   interior_ptr<ListNode ^> ptrToNext = &list;  
   while (*ptrToNext != nullptr) {  
      if ( (*ptrToNext) -> elem == e )  
         *ptrToNext = (*ptrToNext) -> Next;   // delete node  
      else  
         ptrToNext = &(*ptrToNext) -> Next;   // move to next node  
   }  
}  
```  
  
## Voir aussi  
 [Utilisation de l'interopérabilité C\+\+ \(PInvoke implicite\)](../dotnet/using-cpp-interop-implicit-pinvoke.md)