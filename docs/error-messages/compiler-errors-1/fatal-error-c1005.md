---
title: "Erreur irr&#233;cup&#233;rable C1005 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C1005"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C1005"
ms.assetid: 150daf8e-a38a-4669-9c1a-a05b5a1f65ef
caps.latest.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 7
---
# Erreur irr&#233;cup&#233;rable C1005
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

chaîne trop grande pour la mémoire tampon  
  
 Une chaîne dans un fichier intermédiaire du compilateur a entraîné un dépassement de mémoire tampon.  
  
 Vous pouvez obtenir cette erreur quand le paramètre que vous passez aux options de compilateur [\/Fd](../../build/reference/fd-program-database-file-name.md) ou [\/Yl](../../build/reference/yl-inject-pch-reference-for-debug-library.md) est supérieur à 256 octets.