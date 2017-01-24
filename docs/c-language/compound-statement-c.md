---
title: "Instruction composite (C) | Microsoft Docs"
ms.custom: ""
ms.date: "12/05/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "C++"
  - "C"
helpviewer_keywords: 
  - "instructions composées"
  - "instructions, composée"
ms.assetid: 32d1bf86-cbbc-42a9-ba3a-1be1c6c7754c
caps.latest.revision: 8
caps.handback.revision: 8
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Instruction composite (C)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Une instruction composée \(également appelée « bloc »\) correspond généralement au corps d'une autre instruction, telle que l'instruction **if**.  L'article [Déclarations et types](../c-language/declarations-and-types.md) décrit la forme et la signification des déclarations qui peuvent figurer en tête d'une instruction composée.  
  
## Syntaxe  
 *compound\-statement*:  
 **{**  *declaration\-list*  opt *statement\-list* opt **}**  
  
 *declaration\-list*:  
 *declaration*  
  
 *declaration\-list declaration*  
  
 *statement\-list*:  
 s*tatement*  
  
 *statement\-list statement*  
  
 S'il existe des déclarations, elles doivent précéder toutes les instructions.  La portée de chaque identificateur déclaré au début d'une instruction composée s'étend de son point de déclaration jusqu'à la fin du bloc.  Elle est visible dans l'ensemble du bloc à moins qu'une déclaration du même identificateur existe dans un bloc interne.  
  
 Les identificateurs figurant dans une instruction composée sont supposés **auto** à moins qu'ils soient explicitement déclarés autrement à l'aide de **register**, **static** ou `extern`, à l'exception des fonctions, qui peuvent être `extern` uniquement.  Vous pouvez omettre le spécificateur `extern` dans les déclarations de fonction et la fonction sera néanmoins `extern`.  
  
 Le stockage n'est pas alloué et l'initialisation n'est pas autorisée si une variable ou une fonction est déclarée dans une instruction composée au moyen de la classe de stockage `extern`.  La déclaration fait référence à une variable ou fonction externe définie ailleurs.  
  
 Les variables déclarées dans un bloc avec le mot clé **auto** ou **register** sont réaffectées et, si nécessaire, initialisées chaque fois que l'instruction composée est écrite.  Ces variables ne sont pas définies une fois que vous quittez l'instruction composée.  Si une variable déclarée dans un bloc possède l'attribut **static**, elle est initialisée au début de l'exécution du programme et conserve sa valeur tout au long du programme.  Consultez [Classes de stockage](../c-language/c-storage-classes.md) pour plus d'informations sur l'attribut **static**.  
  
 L'exemple suivant illustre une instruction composée :  
  
```  
if ( i > 0 )   
{  
    line[i] = x;  
    x++;  
    i--;  
}  
```  
  
 Dans cet exemple, si `i` est supérieur à 0, toutes les instructions figurant dans l'instruction composée sont exécutées dans l'ordre.  
  
## Voir aussi  
 [Instructions](../c-language/statements-c.md)