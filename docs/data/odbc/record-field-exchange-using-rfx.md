---
title: "Record Field Exchange&#160;: utilisation de RFX | Microsoft Docs"
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
  - "RFX (ODBC), implémenter"
ms.assetid: ada8f043-37e6-4d41-9db3-92c997a61957
caps.latest.revision: 8
caps.handback.revision: 8
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Record Field Exchange&#160;: utilisation de RFX
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

La présente rubrique explique comment utiliser RFX en relation avec les tâches effectuées par l'infrastructure.  
  
> [!NOTE]
>  Cette rubrique s'applique aux classes dérivées de [CRecordset](../../mfc/reference/crecordset-class.md) dans lesquels l'extraction de lignes en bloc n'a pas été implémentée.  Si vous utilisez l'extraction de lignes en bloc, le mécanisme RFX en bloc \(Bulk RFX\) est implémenté.  RFX en bloc est similaire à RFX.  Pour plus d'informations sur les différences, consultez [Recordset : extraction globale d'enregistrements \(ODBC\)](../../data/odbc/recordset-fetching-records-in-bulk-odbc.md).  
  
 Les rubriques suivantes contiennent des informations connexes :  
  
-   [Record Field Exchange : utilisation du code écrit par l'Assistant](../../data/odbc/record-field-exchange-working-with-the-wizard-code.md) présente les principaux composants de RFX et explique le code que l'Assistant Création d'applications MFC et **Add Class** \(comme indiqué dans [Ajout d'un consommateur ODBC MFC](../../mfc/reference/adding-an-mfc-odbc-consumer.md)\) écrivent pour prendre en charge RFX, ainsi que la façon dont vous pourriez modifier le code de l'Assistant.  
  
-   [Record Field Exchange : utilisation des fonctions RFX](../../data/odbc/record-field-exchange-using-the-rfx-functions.md) explique comment écrire les appels de fonction RFX dans la substitution de `DoFieldExchange`.  
  
 Le tableau suivant indique le rôle que vous jouez et ce que la structure accomplit automatiquement.  
  
### Utilisation de RFX : responsabilités respectives  
  
|Vous|L'infrastructure|  
|----------|----------------------|  
|Déclarez les classes du recordset à l'aide d'un Assistant.  Définissez les noms et types de données des membres de données de type champ.|L'Assistant dérive une classe `CRecordset` et écrit automatiquement la substitution de [DoFieldExchange](../Topic/CRecordset::DoFieldExchange.md), y compris l'appel de fonctions RFX pour chaque membre de données de type champ.|  
|\(Facultatif\) Ajoutez manuellement les données membres de paramètre nécessaires à la classe.  Ajoutez manuellement un appel des fonctions RFX à `DoFieldExchange` pour chaque donnée membre de type paramètre, ajouter un appel à [CFieldExchange::SetFieldType](../Topic/CFieldExchange::SetFieldType.md) pour le groupe de paramètres et indiquer le nombre total de paramètres dans [m\_nParams](../Topic/CRecordset::m_nParams.md).  Consultez [Recordset : paramétrage d'un recordset \(ODBC\)](../../data/odbc/recordset-parameterizing-a-recordset-odbc.md).||  
|\(Facultatif\) Liez manuellement les colonnes supplémentaires et les membres de données de type champ.  Incrémentez manuellement [m\_nFields](../Topic/CRecordset::m_nFields.md).  Consultez [Recordset : liaison dynamique de colonnes de données \(ODBC\)](../../data/odbc/recordset-dynamically-binding-data-columns-odbc.md).||  
|Construisez un objet de votre classe de recordset.  Avant d'utiliser l'objet, définissez les valeurs des éventuels membres de données de type paramètre.|Pour des raisons d'efficacité, l'infrastructure lie au préalable les paramètres à l'aide d'ODBC.  Lorsque vous passez les valeurs des paramètres, l'infrastructure les passe à la source de données.  Seules les valeurs des paramètres sont envoyées pour des actualisations, sauf si les chaînes de tri et\/ou de filtre ont changé.|  
|Ouvrez un objet recordset à l'aide de [CRecordset::Open](../Topic/CRecordset::Open.md).|Exécute la requête du recordset, lie les colonnes aux membres de données de type champ de recordset et appelle `DoFieldExchange` pour échanger les données entre le premier enregistrement sélectionné et les membres de données de type champ de recordset.|  
|Parcourez le recordset à l'aide de [CRecordset::Move](../Topic/CRecordset::Move.md) ou d'un menu ou d'une commande de la barre d'outils.|Appelle `DoFieldExchange` pour transférer les données aux données membres de champ à partir du nouvel enregistrement en cours.|  
|Ajoutez, mettez à jour et supprimez des enregistrements.|Appelle `DoFieldExchange` pour transférer les données vers la source de données.|  
  
## Voir aussi  
 [Record Field Exchange \(RFX\)](../../data/odbc/record-field-exchange-rfx.md)   
 [Record Field Exchange : fonctionnement de RFX](../../data/odbc/record-field-exchange-how-rfx-works.md)   
 [Recordset : calculs de totaux et autres résultats de regroupement \(ODBC\)](../../data/odbc/recordset-obtaining-sums-and-other-aggregate-results-odbc.md)   
 [CRecordset Class](../../mfc/reference/crecordset-class.md)   
 [CFieldExchange Class](../../mfc/reference/cfieldexchange-class.md)   
 [Macros, fonctions globales et variables globales](../Topic/Macros,%20Global%20Functions,%20and%20Global%20Variables.md)