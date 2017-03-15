---
title: "Erreur de g&#233;n&#233;ration de projet PRJ0002 | Microsoft Docs"
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
  - "PRJ0002"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "PRJ0002"
ms.assetid: 1c820b1f-9a24-4681-80ed-4fcbfd7caa00
caps.latest.revision: 7
caps.handback.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# Erreur de g&#233;n&#233;ration de projet PRJ0002
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Résultat d'erreur retourné à partir de 'ligne de commande'.  
  
 Une commande, ***ligne de commande***, formée à partir de l'entrée effectuée par l'utilisateur dans la boîte de dialogue **Pages de propriétés**, a retourné un code d'erreur, mais aucune information n'apparaît dans la fenêtre Sortie.  
  
 La correction de cette erreur dépend de l'outil ayant généré l'erreur.  Pour MIDL, vous aurez une idée de l'origine du problème si l'option \/o \(redirection de la sortie\) est définie.  
  
 Un fichier batch, par exemple une étape de build personnalisée ou un événement de build, ne fournissant aucune information sur les conditions d'échec peut également être à l'origine de cette erreur.