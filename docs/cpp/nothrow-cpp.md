---
title: "nothrow (C++) | Microsoft Docs"
ms.custom: ""
ms.date: "12/05/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
f1_keywords: 
  - "nothrow_cpp"
  - "nothrow"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "__declspec (mot clé) (C++), nothrow"
  - "nothrow __declspec (mot clé)"
ms.assetid: 0a475139-459c-4ec6-99e8-7ecd0d7f44a3
caps.latest.revision: 7
caps.handback.revision: 7
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# nothrow (C++)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

**Section spécifique à Microsoft**  
  
 Attribut étendu de `__declspec` qui peut être utilisé dans la déclaration de fonctions.  
  
## Syntaxe  
  
```  
  
return-type __declspec(nothrow) [call-convention] function-name ([argument-list])  
```  
  
## Notes  
 Cet attribut indique au compilateur que la fonction déclarée et les fonctions qu'elle appelle ne lèvent jamais d'exception.  Avec le modèle synchrone de gestion des exceptions, utilisé désormais par défaut, le compilateur peut éliminer les mécanismes de suivi de la durée de vie de certains objets non déroulables dans une telle fonction, et peut réduire considérablement la taille du code.  Compte tenu de la directive de préprocesseur suivante, les trois déclarations de fonction ci\-dessous sont équivalentes :  
  
```  
#define WINAPI __declspec(nothrow) __stdcall   
  
void WINAPI f1();  
void __declspec(nothrow) __stdcall f2();  
void __stdcall f3() throw();  
```  
  
 L'utilisation de `void __declspec(nothrow) __stdcall f2();` a comme avantage que vous pouvez utiliser une définition d'API, telle que celle représentée par l'instruction `#define`, pour spécifier facilement `nothrow` sur un ensemble de fonctions.  La troisième déclaration`, void __stdcall f3() throw();` est la syntaxe définie par la norme C\+\+.  
  
 Consultez [Gestion synchrone des exceptions](http://msdn.microsoft.com/fr-fr/81595fae-d8ab-4c14-9670-8d6639cc0369) pour plus d'informations.  
  
 **FIN de la section spécifique à Microsoft**  
  
## Voir aussi  
 [\_\_declspec](../cpp/declspec.md)   
 [Mots clés C\+\+](../cpp/keywords-cpp.md)