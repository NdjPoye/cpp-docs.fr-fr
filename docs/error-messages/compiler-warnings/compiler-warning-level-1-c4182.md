---
title: "Avertissement du compilateur (niveau&#160;1) C4182 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-csharp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "C4182"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C4182"
ms.assetid: 8970f3c6-e2dd-407e-b2ec-964360eb8b43
caps.latest.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 7
---
# Avertissement du compilateur (niveau&#160;1) C4182
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

le niveau d’imbrication \#include a une profondeur de 'nombre' ; risque de récurrence infinie  
  
 Le compilateur a manqué d’espace sur le tas en raison du nombre de fichiers Include imbriqués. Un fichier Include est imbriqué quand il est inclus dans un autre fichier Include.  
  
 Ce message est un fourni à titre d’information et précède l’erreur [C1076](../../error-messages/compiler-errors-1/fatal-error-c1076.md).