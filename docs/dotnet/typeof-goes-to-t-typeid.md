---
title: "typeof va &#224; T::typeid | Microsoft Docs"
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
  - "__typeof (mot clé)"
  - "typeid (mot clé C++)"
  - "typeid (opérateur)"
ms.assetid: 6a0d35a7-7a1a-4070-b187-cff37cfdc205
caps.latest.revision: 8
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 8
---
# typeof va &#224; T::typeid
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

L'opérateur `typeof` utilisé dans Extensions managées pour C\+\+ a été supplanté par le mot clé `typeid` dans [!INCLUDE[cpp_current_long](../dotnet/includes/cpp_current_long_md.md)].  
  
 Dans les Extensions managées, l'opérateur `__typeof()` retourne l'objet `Type*` associé lorsqu'on lui passe le nom d'un type managé.  Par exemple :  
  
```  
// Creates and initializes a new Array instance.  
Array* myIntArray =   
   Array::CreateInstance( __typeof(Int32), 5 );  
```  
  
 Dans la nouvelle syntaxe, `__typeof` a été remplacé par une forme supplémentaire de `typeid` qui retourne un `Type^` lorsqu'un type managé est spécifié.  
  
```  
// Creates and initializes a new Array instance.  
Array^ myIntArray =   
   Array::CreateInstance( Int32::typeid, 5 );  
```  
  
## Voir aussi  
 [Modification d'ordre général apportée au langage](../dotnet/general-language-changes-cpp-cli.md)   
 [typeid](../windows/typeid-cpp-component-extensions.md)