---
title: "Erreur des outils &#201;diteur de liens LNK1112 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "LNK1112"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "LNK1112"
ms.assetid: 425793d8-37e6-4072-9b6e-c3d4e9c12562
caps.latest.revision: 17
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 17
---
# Erreur des outils &#201;diteur de liens LNK1112
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

le type d’ordinateur du module « type1 » est en conflit avec le type d’ordinateur cible « type2 »  
  
 Les fichiers objets spécifiés en entrée ont été compilés pour différents types d’ordinateurs.  
  
 Par exemple, si vous essayez de lier un fichier objet compilé avec **\/clr** et un fichier objet compilé avec **\/clr:pure** \(type d’ordinateur CEE\), l’éditeur de liens génère l’erreur LNK1112.  
  
 De même, si vous créez un module avec le compilateur [!INCLUDE[vcprx64](../../assembler/inline/includes/vcprx64_md.md)] et un autre module avec le compilateur x86, et que vous tentez de les lier, l’éditeur de liens génère l’erreur LNK1112.  
  
 Une raison possible de cette erreur est que vous développez une application 64 bits, mais que vous n’avez pas installé un des compilateurs 64 bits de Visual C\+\+. Dans ce cas, les configurations 64 bits ne sont pas disponibles. Pour résoudre ce problème, exécutez le programme d’installation pour Visual Studio et installez les composants C\+\+ manquants.  
  
 Cette erreur peut également se produire si vous modifiez la **configuration de la solution active** dans **Configuration Manager**, puis que vous tentez de générer le projet avant de supprimer les fichiers projet intermédiaires. Pour résoudre cette erreur, sélectionnez **Régénérer la Solution** dans le menu **Générer**. Vous pouvez aussi sélectionner **Nettoyer la solution** dans le **Générer**, puis générer la solution.  
  
## Voir aussi  
 [Erreurs et avertissements des outils Éditeur de liens](../../error-messages/tool-errors/linker-tools-errors-and-warnings.md)