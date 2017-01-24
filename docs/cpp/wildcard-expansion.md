---
title: "D&#233;veloppement des caract&#232;res g&#233;n&#233;riques | Microsoft Docs"
ms.custom: ""
ms.date: "12/05/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
f1_keywords: 
  - "_setargv"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "_setargv (fonction)"
  - "caractère générique astérisque"
  - "ligne de commande, traiter des arguments"
  - "ligne de commande, caractères génériques"
  - "caractères génériques de ligne de commande"
  - "point d'interrogation, caractère générique"
ms.assetid: 1a543398-607b-4404-93d1-45d290bde638
caps.latest.revision: 9
caps.handback.revision: 9
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# D&#233;veloppement des caract&#232;res g&#233;n&#233;riques
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

## Section spécifique à Microsoft  
 Vous pouvez utiliser des caractères génériques \(le point d'interrogation \(?\) et l'astérisque \(\*\)\) pour spécifier des arguments de nom de fichier et de chemin d'accès sur la ligne de commande.  
  
 Les arguments de la ligne de commande sont gérés par une routine appelée **\_setargv** \(ou **\_wsetargv** dans l'environnement à caractères larges\), qui, par défaut, ne développe pas les caractères génériques en chaînes séparées dans le tableau de chaînes `argv`.  Pour plus d'informations sur l'activation du développement des caractères génériques, consultez [Développement des arguments avec caractères génériques](../c-language/expanding-wildcard-arguments.md).  
  
## FIN de la section spécifique à Microsoft  
  
## Voir aussi  
 [main : démarrage du programme](../cpp/main-program-startup.md)