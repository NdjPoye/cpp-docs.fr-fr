---
title: "Liaison d&#39;importations | Microsoft Docs"
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
  - "/DELAY:NOBIND (option de l'éditeur de liens)"
  - "DELAY:NOBIND (option de l'éditeur de liens)"
ms.assetid: bb766038-deb1-41b1-bcbc-29a30e8c1e2a
caps.latest.revision: 7
caps.handback.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# Liaison d&#39;importations
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Le comportement par défaut de l'éditeur de liens consiste à créer une table des adresses d'importation pouvant être liées pour la DLL à chargement différé.  Si la DLL est liée, la fonction d'assistance tente d'utiliser les informations liées au lieu d'appeler **GetProcAddress** sur chaque importation référencée.  Si les informations de date ou l'adresse par défaut ne correspondent pas à celles de la DLL chargée, la fonction d'assistance fait comme si la table des adresses d'importation liées était obsolète et poursuit comme si elle n'existait pas.  
  
 Si vous n'envisagez pas de lier les importations à chargement différé de la DLL, le fait de spécifier [\/delay](../../build/reference/delay-delay-load-import-settings.md):nobind sur la ligne de commande de l'éditeur de liens empêche la génération de la table des adresses d'importation liées et ainsi économise de l'espace dans le fichier image.  
  
## Voir aussi  
 [Prise en charge de l'éditeur de liens pour les DLL à chargement différé](../../build/reference/linker-support-for-delay-loaded-dlls.md)