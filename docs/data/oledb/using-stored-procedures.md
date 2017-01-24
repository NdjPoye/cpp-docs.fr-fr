---
title: "Utilisation des proc&#233;dures stock&#233;es | Microsoft Docs"
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
  - "modèles du fournisseur OLE DB, procédures stockées"
  - "OLE DB, procédures stockées"
  - "procédures stockées, à propos des procédures stockées"
  - "procédures stockées, OLE DB"
  - "procédures stockées, Visual C++"
ms.assetid: 90507e4c-eca2-46c9-ad8c-07e10dc1d41b
caps.latest.revision: 16
caps.handback.revision: 16
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Utilisation des proc&#233;dures stock&#233;es
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Une procédure stockée est un objet exécutable stocké dans une base de données.  L'appel d'une procédure stockée est similaire à l'appel d'une commande SQL.  L'utilisation de procédures stockées sur la source de données \(au lieu d'exécuter ou de préparer une instruction dans l'application cliente\) peut offrir plusieurs avantages, notamment les suivants : des performances accrues, une charge réseau réduite ainsi qu'une cohérence et une précision améliorées.  
  
 Une procédure stockée peut avoir un nombre quelconque \(y compris zéro\) de paramètres d'entrée et de sortie, et peut passer une valeur de retour.  Vous pouvez soit coder en dur les valeurs de paramètre comme des valeurs de données spécifiques, soit utiliser un marqueur de paramètre \(point d'interrogation '?'\).  
  
> [!NOTE]
>  Les procédures stockées SQL Server du CLR créées avec Visual C\+\+ doivent être compilées avec l'option **\/clr:safe** du compilateur.  
  
 Le fournisseur OLE DB pour SQL Server \(SQLOLEDB\) prend en charge les mécanismes suivants, que les procédures stockées utilisent pour retourner des données :  
  
-   Chaque instruction SELECT dans la procédure génère un jeu de résultats.  
  
-   La procédure peut retourner des données par l'intermédiaire de paramètres de sortie.  
  
-   La procédure peut avoir un code de retour d'entiers.  
  
> [!NOTE]
>  Vous ne pouvez pas utiliser les procédures stockées avec le fournisseur OLE DB pour Jet car ce fournisseur ne prend pas en charge les procédures stockées ; seules des constantes sont admises dans les chaînes de requêtes.  
  
## Voir aussi  
 [Utilisation des modèles du consommateur OLE DB](../../data/oledb/working-with-ole-db-consumer-templates.md)