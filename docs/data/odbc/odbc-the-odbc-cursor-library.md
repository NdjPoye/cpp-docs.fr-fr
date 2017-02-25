---
title: "ODBC&#160;: biblioth&#232;que de curseurs ODBC | Microsoft Docs"
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
  - "bibliothèque de curseurs (ODBC)"
  - "bibliothèque de curseurs (ODBC), instantanés"
  - "curseurs, bibliothèque de curseurs ODBC"
  - "niveau 1 (pilotes ODBC)"
  - "ODBC (bibliothèque de curseurs)"
  - "ODBC (pilotes), prise en charge du curseur"
  - "ODBC (pilotes), niveau 1"
  - "ODBC, horodatage"
  - "mises à jour positionnées"
  - "positionner les curseurs"
  - "instantanés, prise en charge dans ODBC"
  - "curseurs statiques"
  - "horodatage, colonnes d'horodatage ODBC"
ms.assetid: 6608db92-82b1-4164-bb08-78153c227be3
caps.latest.revision: 9
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 9
---
# ODBC&#160;: biblioth&#232;que de curseurs ODBC
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Cette rubrique décrit la bibliothèque de curseurs ODBC et explique comment l'utiliser.  Pour plus d'informations, consultez :  
  
-   [Bibliothèque de curseurs et les pilotes ODBC de niveau 1](#_core_the_cursor_library_and_level_1_odbc_drivers)  
  
-   [Mises à jour positionnées et colonnes d'horodatage](#_core_positioned_updates_and_timestamp_columns)  
  
-   [Utilisation de la bibliothèque de curseurs](#_core_using_the_cursor_library)  
  
 La bibliothèque de curseurs ODBC est une bibliothèque de liens dynamiques \(DLL, Dynamic\-Link Library\) qui réside entre le gestionnaire de pilote ODBC et le pilote.  Dans la terminologie ODBC, un pilote conserve un « curseur » pour assurer le suivi de son emplacement dans le recordset.  Le curseur marque l'emplacement que vous avez atteint, c'est\-à\-dire l'enregistrement en cours, dans le recordset.  
  
##  <a name="_core_the_cursor_library_and_level_1_odbc_drivers"></a> Bibliothèque de curseurs et les pilotes ODBC de niveau 1  
 La bibliothèque de curseurs ODBC offre aux pilotes de niveau 1 les nouvelles possibilités suivantes :  
  
-   Défilement en avant et en arrière.  Les pilotes de niveau 2 n'ont pas besoin de la bibliothèque de curseurs, car ils peuvent déjà défiler.  
  
-   Prise en charge des instantanés.  La bibliothèque de curseurs gère une mémoire tampon comprenant les enregistrements de l'instantané.  Cette mémoire tampon reflète les suppressions de votre programme et modifications aux enregistrements mais pas les additions, suppressions ou modifications d'autres utilisateurs.  Par conséquent, la capture instantanée est aussi actuelle que la mémoire tampon de la bibliothèque de curseurs uniquement.  La mémoire tampon ne reflète vos propres ajouts qu'au moment où vous appelez **Requery**.  Les feuilles de réponse dynamiques n'utilisent pas la bibliothèque de curseurs.  
  
 La bibliothèque de curseurs vous fournit des instantanés \(curseurs statiques\) même s'ils ne sont normalement pas pris en charge par votre pilote.  Si votre pilote prend déjà en charge les curseurs statiques, vous ne devez pas charger la bibliothèque de curseurs pour pouvoir prendre en charge les instantanés.  Si vous utilisez la bibliothèque de curseurs, vous pouvez seulement utiliser les instantanés et recordsets à défilement en avant.  Si votre pilote prend en charge les feuilles de réponse dynamiques \(curseurs KEYSET\_DRIVEN\) et si vous voulez les utiliser, vous ne devez pas utiliser la bibliothèque de curseurs.  Si vous voulez utiliser les instantanés et les feuilles de réponse dynamiques, vous devez les baser sur deux objets `CDatabase` distincts \(deux connexions différentes\), sauf si votre pilote les prend tous les deux en charge.  
  
##  <a name="_core_positioned_updates_and_timestamp_columns"></a> Mises à jour positionnées et colonnes d'horodatage  
  
> [!NOTE]
>  Les sources de données ODBC sont accessibles via les classes ODBC MFC, comme le décrit cette rubrique, ou via les classes DAO \(Data Access Object\) MFC.  
  
> [!NOTE]
>  Si votre pilote ODBC prend en charge **SQLSetPos**, utilisé par MFC s'il est disponible, cette rubrique ne vous concerne pas.  
  
 La plupart des pilotes de niveau 1 ne prennent pas en charge les mises à jour positionnées.  Ces pilotes reposent sur la bibliothèque de curseurs pour émuler les capacités des pilotes de niveau 2 à cet effet.  La bibliothèque de curseurs émule la prise en charge de mise à jour positionnée en effectuant une mise à jour recherchée sur les champs inchangés.  
  
 Parfois, un recordset peut comprendre une colonne d'horodatage dans un de ces champs inchangés.  L'utilisation de recordsets MFC avec des tables comprenant des colonnes d'horodatage soulève deux problèmes.  
  
 Le premier concerne les instantanés modifiables sur les tables avec des colonnes d'horodatage.  Si la table, à laquelle votre instantané est lié, comprend une colonne d'horodatage, vous devez appeler **Requery** après avoir appelé **Edit** et **Update**.  Sinon, vous ne pourrez peut\-être pas modifier à nouveau le même enregistrement.  Lorsque vous appelez **Edit** puis **Update**, l'enregistrement est écrit dans la source de données et la colonne d'horodatage est mise à jour.  Si vous n'appelez pas **Requery**, la valeur d'horodatage pour l'enregistrement de votre instantané ne correspond plus à l'horodatage adéquat dans la source de données.  Lorsque vous essayez de mettre une nouvelle fois à jour l'enregistrement, la source de données peut empêcher la mise à jour en raison de cette incompatibilité.  
  
 Le second problème concerne les limites de la classe [CTime](../../atl-mfc-shared/reference/ctime-class.md) lorsqu'elle est utilisée avec la fonction `RFX_Date` pour transférer les informations relatives à l'heure et à la date vers et à partir d'une table.  Le traitement de l'objet `CTime` nécessite une certaine charge, sous la forme d'un traitement supplémentaire intermédiaire, lors du transfert de données.  La plage de dates des objets `CTime` peut aussi être trop limitée pour certaines applications.  Une nouvelle version de la fonction `RFX_Date` prend un paramètre **TIMESTAMP\_STRUCT** ODBC au lieu d'un objet `CTime`.  Pour plus d'informations, consultez `RFX_Date` dans [Macros and Globals](../Topic/Macros,%20Global%20Functions,%20and%20Global%20Variables.md) de *MFC Reference*.  
  
##  <a name="_core_using_the_cursor_library"></a> Utilisation de la bibliothèque de curseurs  
 Lorsque vous vous connectez à une source de données, en appelant [CDatabase::OpenEx](../Topic/CDatabase::OpenEx.md) ou [CDatabase::Open](../Topic/CDatabase::Open.md), vous pouvez spécifier si vous voulez utiliser la bibliothèque de curseurs pour la source de données.  Si vous voulez créer des instantanés de cette source de données, définissez pour l'option **CDatabase::useCursorLib** du paramètre `dwOptions` la valeur `OpenEx` ou spécifiez **TRUE** pour le paramètre **bUseCursorLib** dans **Open** \(la valeur par défaut est **TRUE**\).  Si votre pilote ODBC prend en charge les feuilles de réponse dynamiques et si vous voulez ouvrir des feuilles de réponse dynamiques sur cette source de données, n'utilisez pas la bibliothèque de curseurs \(certaines fonctionnalités du pilote, nécessaires pour les feuilles de réponse dynamiques, seraient masquées\).  Dans ce cas, ne spécifiez pas **CDatabase::useCursorLib** dans `OpenEx` ou spécifiez **FALSE** pour le paramètre **bUseCursorLib** dans **Open**.  
  
## Voir aussi  
 [Éléments fondamentaux relatifs à ODBC](../../data/odbc/odbc-basics.md)