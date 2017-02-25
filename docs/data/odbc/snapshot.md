---
title: "Instantan&#233; | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "bibliothèque de curseurs (ODBC), instantanés"
  - "ODBC (curseurs), statiques"
  - "ODBC (bibliothèque de curseurs), instantanés"
  - "ODBC (recordsets), instantanés"
  - "recordsets, instantanés"
  - "instantanés"
  - "instantanés, prise en charge dans ODBC"
  - "curseurs statiques"
ms.assetid: b5293a52-0657-43e9-bd71-fe3785b21c7e
caps.latest.revision: 8
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 8
---
# Instantan&#233;
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Un instantané est un recordset qui reflète une vue statique des données au moment de la création de l'instantané.  Lorsque vous avez ouvert l'instantané et atteint tous les enregistrements, le recordset et leurs valeurs que comprend l'instantané ne varient pas jusqu'à ce que l'instantané soit reconstruit en appelant **Requery**.  
  
> [!NOTE]
>  Cette rubrique s'applique aux classes ODBC MFC.  Si vous utilisez les classes DAO MFC plutôt que les classes ODBC MFC, consultez [CDaoRecordset::Open](../Topic/CDaoRecordset::Open.md) pour plus de détails sur les recordsets de type instantané.  
  
 Vous pouvez créer des instantanés modifiables ou en lecture seule avec les classes de base de données.  Contrairement à une feuille de réponse dynamique, un instantané modifiable ne reflète pas les modifications effectuées par d'autres utilisateurs aux valeurs d'enregistrement, mais reflète les mises à jour et les suppressions effectuées par votre programme.  Les enregistrements ajoutés à un instantané ne sont pas visibles dans l'instantané avant l'appel de **Requery**.  
  
> [!TIP]
>  Un instantané est un curseur statique ODBC.  Les curseurs statiques n'obtiennent aucune ligne de données jusqu'à ce que l'enregistrement soit affiché.  Pour vous assurer que tous les enregistrements sont immédiatement récupérés, affichez la fin de votre recordset, puis faites\-le défiler pour afficher le premier enregistrement souhaité.  Notez cependant que le défilement vers la fin du recordset entraîne une charge supplémentaire et peut diminuer la performance.  
  
 Les instantanés sont plus utiles lorsque les données doivent rester fixes lors de vos opérations, par exemple lorsque vous générez un rapport ou effectuez des calculs.  Même dans ce cas, la source de données peut différer considérablement de votre instantané ; vous pourriez être amené à le régénérer de temps en temps.  
  
 La prise en charge d'instantané est basée sur la bibliothèque de curseurs ODBC, qui procure des curseurs statiques et des mises à jour positionnées \(nécessaires pour la mise à jour\) pour tout pilote de niveau 1.  La DLL de la bibliothèque de curseurs doit être chargée en mémoire pour assurer cette prise en charge.  Lorsque vous construisez un objet `CDatabase` et appelez sa fonction membre `OpenEx`, vous devez spécifier l'option **CDatabase::useCursorLib** du paramètre `dwOptions`.  Si vous appelez la fonction membre **Open**, la bibliothèque de curseurs est chargée par défaut.  Si vous utilisez des feuilles de réponse dynamiques à la place d'instantanés, vous ne voulez pas que la bibliothèque de curseurs soit chargée.  
  
 Les instantanés ne sont disponibles que si la bibliothèque de curseurs ODBC était chargée lors de la construction de l'objet `CDatabase` ou si le pilote ODBC que vous utilisez prend en charge les curseurs statiques.  
  
> [!NOTE]
>  Pour certains pilotes ODBC, les instantanés \(curseurs statiques\) peuvent ne pas être modifiables.  Vérifiez la documentation du pilote pour les types de curseurs pris en charge et les types d'accès concurrentiel qu'ils prennent en charge.  Pour pouvoir mettre à jour les instantanés, assurez\-vous de charger la bibliothèque de curseurs en mémoire lorsque vous créez un objet `CDatabase`.  Pour plus d'informations, consultez [ODBC : bibliothèque de curseurs ODBC](../../data/odbc/odbc-the-odbc-cursor-library.md).  
  
> [!NOTE]
>  Si vous voulez utiliser les instantanés et les feuilles de réponse dynamiques, vous devez les baser sur deux objets `CDatabase` distincts \(deux connexions différentes\).  
  
 Pour plus d'informations sur les propriétés que les instantanés partagent avec tous les recordsets, consultez [Recordset \(ODBC\)](../../data/odbc/recordset-odbc.md).  Pour plus d'informations sur ODBC et les instantanés*,* y compris la bibliothèque de curseurs ODBC, consultez [ODBC](../../data/odbc/odbc-basics.md).  
  
## Voir aussi  
 [ODBC \(Open Database Connectivity\)](../../data/odbc/open-database-connectivity-odbc.md)