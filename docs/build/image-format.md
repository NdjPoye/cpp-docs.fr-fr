---
title: "Format d&#39;image | Microsoft Docs"
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
ms.assetid: 3ca3654b-42fe-4253-9f2e-723644041aa0
caps.latest.revision: 8
caps.handback.revision: 8
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# Format d&#39;image
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Le format d'image exécutable est PE32\+.  Les images exécutables \(à la fois DLL et EXE\) sont limitées à une taille maximale de 2 gigaoctets ; par conséquent, l'adressage relatif avec un décalage de 32 bits peut être utilisé pour adresser des données d'image statiques.  Ces données comprennent la table des adresses d'importation, les constantes de chaîne, les données globales statiques, etc.  
  
## Voir aussi  
 [Conventions des logiciels x64](../build/x64-software-conventions.md)