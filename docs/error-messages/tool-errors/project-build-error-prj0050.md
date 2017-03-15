---
title: "Erreur de g&#233;n&#233;ration de projet PRJ0050 | Microsoft Docs"
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
  - "PRJ0050"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "PRJ0050"
ms.assetid: ceef3b37-0acf-4abd-ac62-aa830b4fa145
caps.latest.revision: 4
caps.handback.revision: 4
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# Erreur de g&#233;n&#233;ration de projet PRJ0050
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Échec de l'inscription de la sortie.Vérifiez que vous avez les autorisations appropriées pour modifier le Registre.  
  
 Le système de génération Visual C\+\+ n'a pas pu enregistrer la sortie de la génération \(dll ou .exe\).  Vous devez ouvrir une session en tant qu'administrateur pour modifier le Registre.  
  
 Si vous générez un .dll, vous pouvez essayer de l'enregistrer manuellement à l'aide de regsvr32.exe. Les informations sur les causes de l'échec de la génération doivent s'afficher.  
  
 Si vous ne générez pas de .dll, recherchez la commande dans le journal de génération qui provoque une erreur.