---
title: "Litt&#233;raux de cha&#238;ne C | Microsoft Docs"
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
  - "chaînes littérales, C"
  - "littéraux de chaîne, syntaxe"
  - "chaînes (C++), littéraux de chaîne"
ms.assetid: 4b05523e-49a2-4900-b21a-754350af3328
caps.latest.revision: 11
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 11
---
# Litt&#233;raux de cha&#238;ne C
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Un littéral de chaîne est une séquence de caractères du jeu de caractères source placée entre guillemets \(**" "**\).  Les littéraux de chaîne servent à représenter une séquence de caractères qui, une fois combinés, forment une chaîne terminée par le caractère Null.  Vous devez toujours faire précéder les littéraux de chaîne étendue de la lettre **L**.  
  
## Syntaxe  
 *string\-literal* :  
 **"** *s\-char\-sequence*  opt               **"**  
  
 **L"** *s\-char\-sequence*  opt               **"**  
  
 *s\-char\-sequence* :  
 *s\-char*  
  
 *s\-char\-sequence s\-char*  
  
 *s\-char* :  
 Tout membre du jeu de caractères source à l'exception du guillemet double \("\), de la barre oblique inverse \(\\\) ou du caractère de saut de ligne  
  
 *escape\-sequence*  
  
 L'exemple ci\-dessous est un littéral de chaîne simple :  
  
```  
char *amessage = "This is a string literal.";  
```  
  
 Tous les codes d'échappement répertoriés dans le tableau [Séquences d'échappement](../c-language/escape-sequences.md) sont valides dans les littéraux de chaîne.  Pour représenter un guillemet double dans un littéral de chaîne, utilisez la séquence d'échappement **\\"**.  Le guillemet simple \(**'**\) peut être représenté sans séquence d'échappement.  La barre oblique inverse \(**\\**\) doit être suivie d'une seconde barre oblique inverse \(**\\\\**\) lorsqu'elle apparaît dans une chaîne.  Lorsqu'une barre oblique inverse apparaît à la fin d'une ligne, elle est toujours interprétée comme un caractère de continuation de ligne.  
  
## Voir aussi  
 [Éléments de C](../c-language/elements-of-c.md)