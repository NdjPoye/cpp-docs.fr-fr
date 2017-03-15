---
title: "&#201;valuateur d&#39;expression, erreur CXX0036 | Microsoft Docs"
ms.custom: ""
ms.date: "12/05/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "CXX0036"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CAN0036"
  - "CXX0036"
ms.assetid: 383404be-df5b-4eec-b113-df21bb5d269d
caps.latest.revision: 6
caps.handback.revision: 6
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# &#201;valuateur d&#39;expression, erreur CXX0036
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

spécification de contexte {...} incorrecte  
  
 Ce message peut être généré par plusieurs erreurs d'utilisation de l'opérateur de contexte \(**{}**\).  
  
-   La syntaxe spécifiée pour l'opérateur de contexte \(**{}**\) est incorrecte.  
  
     La syntaxe correcte est la suivante :  
  
     {*fonction*,*module*,*dll*}*expression*  
  
     Elle spécifie le contexte d'*expression*.  L'opérateur de contexte présente la même priorité et la même utilisation qu'une conversion de type.  
  
     Vous pouvez omettre les virgules de fin.  Si *fonction*, *module* ou *dll* contient une virgule littérale, vous devez placer l'ensemble du nom entre parenthèses.  
  
-   Le nom de la fonction n'est pas correctement orthographié ou il n'existe pas dans le module ou la bibliothèque de liens dynamiques spécifiés.  
  
     Dans la mesure où le langage C respecte la casse, *fonction* doit être fourni avec une casse strictement identique à celle de sa définition dans le source.  
  
-   Le module ou la DLL est introuvable.  
  
     Vérifiez le chemin complet du module ou de la DLL spécifiés.  
  
 Erreur identique à CAN0036.