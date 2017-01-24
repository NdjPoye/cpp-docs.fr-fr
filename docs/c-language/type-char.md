---
title: "char, type | Microsoft Docs"
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
  - "char (mot clé) (C)"
  - "char (type)"
  - "unsigned char (mot clé) (C)"
ms.assetid: a5da0866-e780-4793-be87-15a8426e7ea0
caps.latest.revision: 7
caps.handback.revision: 7
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# char, type
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Le type `char` est utilisé pour stocker la valeur entière d'un membre du jeu de caractères qui peut être représenté.  Cette valeur est le code ASCII correspondant au caractère spécifié.  
  
 **Section spécifique à Microsoft**  
  
 Les valeurs de caractère de type `unsigned char` ont une plage de 0 à 0xFF hexadécimal.  La valeur **signed char** a une plage de 0x80 à 0x7F.  En valeur décimale, ces plages s'étendent de 0 à 255 et de \-128 à \+127, respectivement.  L'option \/J du compilateur modifie le paramètre par défaut en remplaçant **signed** par `unsigned`.  
  
 **FIN de la section spécifique à Microsoft**  
  
## Voir aussi  
 [Stockage de types de base](../c-language/storage-of-basic-types.md)