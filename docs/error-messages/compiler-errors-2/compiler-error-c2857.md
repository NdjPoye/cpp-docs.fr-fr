---
title: "Erreur du compilateur C2857 | Microsoft Docs"
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
  - "C2857"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C2857"
ms.assetid: b57302bd-58ec-45ae-992a-1e282d5eeccc
caps.latest.revision: 7
caps.handback.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# Erreur du compilateur C2857
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

L'instruction '\#include' spécifiée avec l'option de ligne de commande \/YcNomFichier n'a pu être trouvée dans le fichier source  
  
 L'option [\/Yc](../../build/reference/yc-create-precompiled-header-file.md) spécifie le nom d'un fichier include qui n'est pas inclus dans le fichier source en cours de compilation.  
  
 Cette erreur peut être provoquée par une instruction `#include` dans un bloc de compilation conditionnelle qui n'est pas compilé.