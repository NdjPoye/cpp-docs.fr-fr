---
title: "Constantes caract&#232;re C | Microsoft Docs"
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
  - "guillemet simple (')"
  - "caractères, constantes"
  - "constantes, caractère"
  - "guillemet simple"
ms.assetid: 388ae7d7-2c3a-44d6-a507-63f541ecd2da
caps.latest.revision: 11
caps.handback.revision: 11
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Constantes caract&#232;re C
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Une constante caractère est formée en plaçant un caractère du jeu de caractères représentable entre guillemets simples \(**' '**\).  Les constantes caractère sont utilisées pour représenter des caractères dans le [jeu de caractères d'exécution](../c-language/execution-character-set.md).  
  
## Syntaxe  
 *character\-constant*:  
 **'** *c\-char\-sequence* **'**  
  
 **L'** *c\-char\-sequence* **'**  
  
 *c\-char\-sequence*:  
 *c\-char*  
  
 *c\-char\-sequence c\-char*  
  
 *c\-char*:  
 Tout membre du jeu de caractères source à l'exception du guillemet simple \(**'**\), de la barre oblique inverse \(**\\**\) ou du caractère de saut de ligne  
  
 *escape\-sequence*  
  
 *escape\-sequence*:  
 *simple\-escape\-sequence*  
  
 *octal\-escape\-sequence*  
  
 *hexadecimal\-escape\-sequence*  
  
 *simple\-escape\-sequence*: un des éléments suivants :  
 **\\a \\b \\f \\n \\r \\t \\v**  
  
 **\\' \\" \\\\ \\?**  
  
 *octal\-escape\-sequence*:  
 **\\**  *octal\-digit*  
  
 **\\**  *octal\-digit octal\-digit*  
  
 **\\**  *octal\-digit octal\-digit octal\-digit*  
  
 *hexadecimal\-escape\-sequence*:  
 **\\x**  *hexadecimal\-digit*  
  
 *hexadecimal\-escape\-sequence hexadecimal\-digit*  
  
## Voir aussi  
 [Constantes C](../c-language/c-constants.md)