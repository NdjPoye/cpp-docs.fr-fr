---
title: "Stockage de litt&#233;raux de cha&#238;ne | Microsoft Docs"
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
  - "littéraux de chaîne, stockage"
ms.assetid: ba5e4d2c-d456-44b3-a8ca-354af547ac50
caps.latest.revision: 9
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 9
---
# Stockage de litt&#233;raux de cha&#238;ne
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Les caractères d'une chaîne littérale sont stockés dans l'ordre à des emplacements de mémoire contigus.  Une séquence d'échappement \(telle que **\\\\** ou **\\"**\) dans un littéral de chaîne compte comme un caractère unique.  Un caractère Null \(représenté par la séquence d'échappement **\\0**\) est ajouté automatiquement et marque la fin de chaque littéral de chaîne. \(Cela se produit pendant la [phase de traduction](../preprocessor/phases-of-translation.md) 7.\) Notez que le compilateur peut ne pas stocker deux chaînes identiques à deux adresses différentes.  [\/GF](../build/reference/gf-eliminate-duplicate-strings.md) oblige le compilateur à placer une copie unique des chaînes identiques dans le fichier exécutable.  
  
## Remarques  
 **Section spécifique à Microsoft**  
  
 Les chaînes ont une durée de stockage statique.  Pour plus d'informations sur la durée de stockage, consultez [Classes de stockage](../c-language/c-storage-classes.md).  
  
 **FIN de la section spécifique à Microsoft**  
  
## Voir aussi  
 [Littéraux de chaîne C](../c-language/c-string-literals.md)