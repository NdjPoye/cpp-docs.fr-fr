---
title: "Comment&#160;: utiliser un type natif dans une compilation /clr | Microsoft Docs"
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
  - "/clr (option du compilateur C++), utiliser des types natifs"
  - "compilation, types natifs dans /clr"
ms.assetid: 3a505c90-4adb-4942-9cf9-7d1fdcbc01e7
caps.latest.revision: 3
caps.handback.revision: 3
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Comment&#160;: utiliser un type natif dans une compilation /clr
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Vous pouvez définir un type natif dans une compilation **\/clr** et toute utilisation de ce type natif depuis l'assembly sera valide.  Toutefois, les types natifs ne seront pas utilisables depuis des métadonnées référencées.  
  
 Chaque assembly doit contenir la définition de chaque type natif qu'il utilisera.  
  
 Pour plus d'informations, consultez [\/clr \(Compilation pour le Common Language Runtime\)](../build/reference/clr-common-language-runtime-compilation.md).  
  
## Exemple  
 Cet exemple crée un composant qui définit et utilise un type natif.  
  
```  
// use_native_type_in_clr.cpp  
// compile with: /clr /LD  
public struct NativeClass {  
   static int Test() { return 98; }  
};  
  
public ref struct ManagedClass {  
   static int i = NativeClass::Test();  
   void Test() {  
      System::Console::WriteLine(i);  
   }  
};  
```  
  
## Exemple  
 Cet exemple définit un client qui consomme le composant.  Remarquez qu'accéder au type natif constitue une erreur, à moins que cela ne soit défini dans le module \(compiland\).  
  
```  
// use_native_type_in_clr_2.cpp  
// compile with: /clr  
#using "use_native_type_in_clr.dll"  
// Uncomment the following 3 lines to resolve.  
// public struct NativeClass {  
//    static int Test() { return 98; }  
// };  
  
int main() {  
   ManagedClass x;  
   x.Test();  
  
   System::Console::WriteLine(NativeClass::Test());   // C2653  
}  
```  
  
## Voir aussi  
 [Utilisation de l'interopérabilité C\+\+ \(PInvoke implicite\)](../dotnet/using-cpp-interop-implicit-pinvoke.md)