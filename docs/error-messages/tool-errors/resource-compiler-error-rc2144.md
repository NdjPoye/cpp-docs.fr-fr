---
title: "Erreur RC2144 du compilateur de ressources  | Microsoft Docs"
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
  - "RC2144"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "RC2144"
ms.assetid: 1b3ff39a-92cd-4a04-b1a3-b1fa6a805813
caps.latest.revision: 8
caps.handback.revision: 8
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# Erreur RC2144 du compilateur de ressources 
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

L'ID DE LANGUE PRINCIPALE n'est pas un numéro  
  
 L'ID DE LANGUE PRINCIPALE doit être un ID de langue hexadécimal.  Consultez [Chaînes de langues et de pays\/régions](../../c-runtime-library/locale-names-languages-and-country-region-strings.md) dans la *Référence de la bibliothèque Runtime* pour obtenir la liste des ID de langue valides.  
  
 Cette erreur peut aussi se produire si des ressources ont été ajoutées et supprimées à partir du fichier .RC à l'aide d'un outil.  Pour résoudre ce problème, ouvrez le fichier .RC dans un éditeur de texte et nettoyez manuellement les ressources non utilisées.