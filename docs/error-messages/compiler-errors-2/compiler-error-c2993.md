---
title: "Erreur du compilateur C2993 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C2993"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C2993"
ms.assetid: 4ffd2b78-654b-46aa-95a6-b62101cf91c8
caps.latest.revision: 8
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 8
---
# Erreur du compilateur C2993
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'identificateur' : type non conforme pour le paramètre de modèle sans type 'paramètre'  
  
 Vous ne pouvez pas déclarer un modèle avec un argument de type structure ou union.  Utilisez des pointeurs pour passer les structures et les unions sous forme de paramètres de modèle.  
  
 L'exemple suivant génère l'erreur C2993 :  
  
```  
// C2993.cpp  
// compile with: /c  
// C2993 expected  
struct MyStruct {  
   int a;char b;  
};  
  
template <class T, struct MyStruct S>   // C2993  
  
// try the following line instead  
// template <class T, struct MyStruct * S>  
class CMyClass {};  
```  
  
 Cette erreur peut également être due à la mise en conformité du compilateur pour Visual Studio .NET 2003 : les paramètres de modèle sans type à virgule flottante ne sont plus autorisés.  Le standard C\+\+ ne permet pas les paramètres de modèle sans type à virgule flottante.  
  
 S'il s'agit d'un modèle de fonction, utilisez un argument de fonction pour passer le paramètre de modèle sans type à virgule flottante \(ce code sera valide dans les versions Visual Studio .NET 2003 et Visual Studio .NET de Visual C\+\+\).  S'il s'agit qu'un modèle de classe, il n'existe pas de solution facile à mettre en œuvre.  
  
```  
// C2993b.cpp  
// compile with: /c  
template<class T, float f> void func(T) {}   // C2993  
  
// OK  
template<class T>   void func2(T, float) {}  
```