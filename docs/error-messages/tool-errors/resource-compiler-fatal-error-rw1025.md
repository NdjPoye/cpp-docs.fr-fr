---
title: "Erreur irr&#233;cup&#233;rable RW1025 du compilateur de ressources  | Microsoft Docs"
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
  - "RW1025"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "RW1025"
ms.assetid: 561a02af-e7e0-442a-8ad3-a00b2ca1b62e
caps.latest.revision: 6
caps.handback.revision: 6
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# Erreur irr&#233;cup&#233;rable RW1025 du compilateur de ressources 
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Espace du tas far insuffisant  
  
 Vérifiez si des logiciels résidents utilisent trop d'espace.  Le programme CHKDSK permet de vérifier la quantité de mémoire dont vous disposez.  
  
 Si vous créez un fichier de ressources volumineux, répartissez le script de ressources sur deux fichiers.  Une fois les deux fichiers .res créés, assemblez\-les à l'aide de la ligne de commande MS\-DOS suivante :  
  
```  
copy first.res /b + second.res /b full.res  
```