---
title: "Tableau Param et points de suspension | Microsoft Docs"
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
  - "surcharge de fonction, correspondances d'arguments"
ms.assetid: 492e3f6c-1c4c-4e0c-a358-72f2d39c30be
caps.latest.revision: 9
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 9
---
# Tableau Param et points de suspension
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

La priorité du tableau param pour résoudre des appels de fonction surchargés a été modifiée entre Extensions managées pour C\+\+ et [!INCLUDE[cpp_current_long](../dotnet/includes/cpp_current_long_md.md)].  
  
 En Extensions managées comme dans la nouvelle syntaxe, il n'existe aucune prise en charge explicite du tableau param que C\# et [!INCLUDE[vbprvb](../dotnet/includes/vbprvb_md.md)] prennent en charge.  À la place, un tableau ordinaire se signale à l'aide d'un attribut, comme ceci :  
  
```  
void Trace1( String* format, [ParamArray]Object* args[] );  
void Trace2( String* format, Object* args[] );  
```  
  
 Bien que les deux procédures paraissent identiques, l'attribut `ParamArray` marque ceci pour C\# ou d'autres langages de CLR comme un tableau prenant un nombre variable d'éléments à chaque appel.  La modification de comportement des programmes entre Extensions managées et la nouvelle syntaxe se trouve dans la résolution d'un jeu de fonctions surchargées dans lequel une instance déclare des points de suspension et une seconde déclare un attribut `ParamArray`, comme dans l'exemple suivant fourni par Artur Laksberg.  
  
```  
int fx(...); // 1  
int fx( [ParamArray] Int32[] ); // 2  
```  
  
 En Extensions managées, les points de suspension avaient priorité sur l'attribut, ce qui faisait sens puisque l'attribut n'est pas un aspect formel du langage.  Mais dans la nouvelle syntaxe, le tableau param est maintenant pris en charge directement dans le langage et il est prioritaire sur les points de suspension parce qu'il est plus fortement typé.  En Extensions managées, l'appel  
  
```  
fx( 1, 2 );  
```  
  
 résout donc sur `fx(…)` tandis que dans la nouvelle syntaxe, il résout sur l'instance de `ParamArray`.  Au cas improbable où le comportement de votre programme dépendrait de l'appel de l'instance de points de suspension plutôt que du `ParamArray`, vous devrez modifier soit la signature, soit l'appel.  
  
## Voir aussi  
 [Modification d'ordre général apportée au langage](../dotnet/general-language-changes-cpp-cli.md)