---
title: "Erreur irr&#233;cup&#233;rable C1352 | Microsoft Docs"
ms.custom: ""
ms.date: "12/05/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-csharp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "C1352"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C1352"
ms.assetid: d044e8b0-b6ef-4d57-8eb5-6254071be707
caps.latest.revision: 7
caps.handback.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# Erreur irr&#233;cup&#233;rable C1352
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Code MSIL non valide ou endommagé dans la fonction 'fonction' à partir de 'fichier' de module  
  
 Un fichier .netmodule a été passé au compilateur, mais le compilateur a détecté que le fichier était endommagé.  Demandez à l’auteur du fichier .netmodule de rechercher l’origine du problème.  
  
 Le compilateur ne recherche pas tous les types d’endommagements dans les fichiers .netmodule qu’il vérifie.  Toutefois, il vérifie que tous les chemins de contrôle d’une fonction contiennent bien une instruction return.  
  
 Pour plus d’informations, consultez [Fichiers .netmodule en tant qu’entrée de l’Éditeur de liens](../../build/reference/netmodule-files-as-linker-input.md).