---
title: "Utilisation des accesseurs manuels | Microsoft Docs"
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
  - "accesseurs (C++), manuels"
  - "gestion des commandes, modèles OLE DB"
  - "accesseurs manuels"
ms.assetid: 29f00a89-0240-482b-8413-4120b9644672
caps.latest.revision: 7
caps.handback.revision: 7
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Utilisation des accesseurs manuels
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Lors de la manipulation d'une commande inconnue, vous devez exécuter quatre opérations :  
  
-   Déterminer les paramètres  
  
-   Exécuter la commande  
  
-   Déterminer les colonnes de sortie  
  
-   Vérifier s'il y a plusieurs jeux de lignes de retour  
  
 Pour exécuter ces opérations à l'aide des modèles du consommateur OLE DB, utilisez la classe `CManualAccessor` et suivez la procédure ci\-dessous :  
  
1.  Ouvrez un objet `CCommand` à l'aide de la classe `CManualAccessor` comme paramètre de modèle.  
  
    ```  
    CCommand<CManualAccessor, CRowset, CMultipleResults> rs;  
    ```  
  
2.  Interrogez la session pour l'interface **IDBSchemaRowset** et utilisez le jeu de lignes des paramètres de la procédure.  Si l'interface **IDBSchemaRowset** n'est pas disponible, recherchez l'interface `ICommandWithParameters`.  Pour plus d'informations, appelez `GetParameterInfo`.  Si aucune interface n'est disponible, vous pouvez supposer qu'il n'existe pas de paramètres.  
  
3.  Pour chaque paramètre, appelez `AddParameterEntry` pour ajouter les paramètres et les définir.  
  
4.  Ouvrez le jeu de lignes mais attribuez la valeur **false** au paramètre de liaison.  
  
5.  Appelez `GetColumnInfo` pour récupérer les colonnes de sortie.  Utilisez `AddBindEntry` pour ajouter la colonne de sortie à la liaison.  
  
6.  Appelez `GetNextResult` pour déterminer si d'autres jeux de lignes sont disponibles.  Répétez les étapes 2 à 5.  
  
 Pour obtenir un exemple d'accesseur manuel, consultez **CDBListView::CallProcedure** dans l'exemple [DBVIEWER](http://msdn.microsoft.com/fr-fr/07620f99-c347-4d09-9ebc-2459e8049832).  
  
## Voir aussi  
 [Utilisation des accesseurs](../../data/oledb/using-accessors.md)