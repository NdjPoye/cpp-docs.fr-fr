---
title: "Dump des importations &#224; chargement diff&#233;r&#233; | Microsoft Docs"
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
helpviewer_keywords: 
  - "importations à chargement différé"
  - "importations à chargement différé, vider"
  - "importations (à chargement différé)"
ms.assetid: f766acf4-9df8-4b85-8cf6-0be3ffc4c124
caps.latest.revision: 7
caps.handback.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# Dump des importations &#224; chargement diff&#233;r&#233;
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Les importations à chargement différé peuvent faire l'objet d'un dump à l'aide de [dumpbin \/imports](../../build/reference/imports-dumpbin.md) et présentent des informations légèrement différentes de celles qui sont fournies par les importations standard.  Elles sont mises à part dans leur propre section de dump \/imports et sont explicitement étiquetées en tant qu'importations à chargement différé.  Lorsque des informations de déchargement figurent dans l'image, cela est pris en compte.  En présence d'informations de liaison, les informations heure\/date de la DLL cible sont notées avec les adresses liées des importations.  
  
## Voir aussi  
 [Prise en charge de l'éditeur de liens pour les DLL à chargement différé](../../build/reference/linker-support-for-delay-loaded-dlls.md)