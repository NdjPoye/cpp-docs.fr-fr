---
title: "Caract&#232;res sp&#233;ciaux dans un makefile | Microsoft Docs"
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
  - "macros, caractères spéciaux"
  - "makefiles, caractères spéciaux"
  - "programme NMAKE, caractères spéciaux"
  - "caractères spéciaux, dans les macros NMAKE"
ms.assetid: 92c34ab5-ca6b-4fc0-bcf4-3172eaeda9f0
caps.latest.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 7
---
# Caract&#232;res sp&#233;ciaux dans un makefile
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Pour utiliser un caractère spécial NMAKE en tant que caractère littéral, faites\-le précéder du signe insertion \(^\).  NMAKE ignore les signes d'insertion qui précèdent d'autres caractères.  Les caractères spéciaux sont les suivants :  
  
 `:  ;  #  (  )  $  ^  \  {  }  !  @  —`  
  
 Un signe insertion \(^\) placé dans une chaîne mise entre guillemets est considéré comme un signe insertion littéral.  Un signe insertion placé à la fin d'une ligne insère un caractère de saut de ligne littéral dans une chaîne ou une macro.  
  
 Dans les macros, une barre oblique inverse \(\\\) suivie par un caractère de saut de ligne est remplacée par un espace.  
  
 Dans les commandes, un symbole de pourcentage \(%\) est un spécificateur de fichier.  Pour représenter littéralement le signe % dans une commande, définissez non pas un seul signe de pourcentage mais deux \(%%\).  Dans d'autres situations, NMAKE interprète littéralement un signe % unique, mais interprète toujours un double signe %% comme un simple signe %.  Par conséquent, pour une représentation littérale du signe %%, spécifiez soit trois signes de pourcentage \(%%%\) soit quatre signes de pourcentage \(%%%%\).  
  
 Pour utiliser le signe dollar \($\) en tant que caractère littéral dans une commande, définissez deux signes dollar \($$\).  Cette méthode est également valable pour toutes les situations où ^$ fonctionne.  
  
## Voir aussi  
 [Contenu d'un makefile](../build/contents-of-a-makefile.md)