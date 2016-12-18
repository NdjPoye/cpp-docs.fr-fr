---
title: "Erreur du compilateur C2567 | Microsoft Docs"
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
  - "C2567"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C2567"
ms.assetid: 9c140ac9-7059-47e6-9ba1-e7939c8c0dc3
caps.latest.revision: 4
caps.handback.revision: 4
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# Erreur du compilateur C2567
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

impossible d'ouvrir les métadonnées dans 'fichier' ; le fichier a peut\-être été supprimé ou déplacé  
  
 Un fichier de métadonnées référencé dans la source \(avec `#using`\) n'a pas été détecté dans le même répertoire par le processus principal et le processus frontal du compilateur.  Pour plus d'informations, consultez [\#using, directive](../../preprocessor/hash-using-directive-cpp.md).  
  
 L'erreur C2567 peut être générée si vous compilez avec **\/c** sur un ordinateur, puis tentez de générer du code au moment de la liaison sur un autre ordinateur.  Pour plus d'informations, consultez [\/LTCG \(Génération de code durant l'édition de liens\)](../../build/reference/ltcg-link-time-code-generation.md).  
  
 Elle peut également indiquer que votre ordinateur ne disposait plus de mémoire disponible.  
  
 Pour corriger cette erreur, assurez\-vous que le fichier de métadonnées se trouve dans le même emplacement de répertoire pour toutes les phases du processus de génération.