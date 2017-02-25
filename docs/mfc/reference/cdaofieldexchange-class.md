---
title: "CDaoFieldExchange Class | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "CDaoFieldExchange"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CDaoFieldExchange class"
  - "DAO (Data Access Objects), record field exchange (DFX)"
  - "processus DFX (DAO record field exchange)"
  - "processus DFX (DAO record field exchange), DAO Record Field Exchange"
  - "exchanging data between databases and recordsets"
  - "field exchange"
  - "field exchange, record for DAO classes"
  - "RFX (Record Field Exchange)"
  - "RFX (Record Field Exchange), DAO classes"
ms.assetid: 350a663e-92ff-44ab-ad53-d94efa2e5823
caps.latest.revision: 23
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 24
---
# CDaoFieldExchange Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Prend en charge les routines du processus DFX \(DFX\) utilisés par les classes de bases de données DAO.  
  
## Syntaxe  
  
```  
class CDaoFieldExchange  
```  
  
## Membres  
  
### Méthodes publiques  
  
|Nom|Description|  
|---------|-----------------|  
|[CDaoFieldExchange::IsValidOperation](../Topic/CDaoFieldExchange::IsValidOperation.md)|Retourne une valeur différente de zéro si l'opération en cours est appropriée pour le type de champ qui est mis à jour.|  
|[CDaoFieldExchange::SetFieldType](../Topic/CDaoFieldExchange::SetFieldType.md)|Spécifie le type de donnée membre du recordset — colonne ou paramètre — représenté par tous les appels suivants à DFX s'exécute jusqu'à l'appel suivant à `SetFieldType`.|  
  
### Données membres publiques  
  
|Nom|Description|  
|---------|-----------------|  
|[CDaoFieldExchange::m\_nOperation](../Topic/CDaoFieldExchange::m_nOperation.md)|L'exécution de DFX exécutée par l'appel actif à la fonction membre d' `DoFieldExchange` du recordset.|  
|[CDaoFieldExchange::m\_prs](../Topic/CDaoFieldExchange::m_prs.md)|Un pointeur vers le recordset sur lequel les opérations de DFX sont exécutées.|  
  
## Notes  
 `CDaoFieldExchange` n'a pas de classe de base.  
  
 Utilisez cette classe si vous écrivez des routines d'échange de données pour les types de données personnalisés ; sinon, vous n'utiliserez pas directement cette classe.  Données d'échanges de DFX entre les données membres de champ de votre objet de [CDaoRecordset](../../mfc/reference/cdaorecordset-class.md) et les champs correspondants de l'enregistrement en cours sur la source de données.  DFX gère l'échange dans les deux sens, de la source de données et à la source de données.  Consultez [note technique 53](../../mfc/tn053-custom-dfx-routines-for-dao-database-classes.md) pour plus d'informations sur les routines DFX personnalisés d'écriture.  
  
> [!NOTE]
>  Les classes de bases de données DAO sont séparées des classes de base de données MFC basée sur \(Open Database Connectivity\).  Tous les noms de classes de bases de données DAO ont le préfixe « CDao ».  Vous pouvez encore accéder aux sources de données ODBC avec les classes DAO.  En général les classes DAO MFC basée sur sont plus qui gèrent les classes ODBC MFC basée sur.  Les classes DAO peuvent accéder aux données, notamment via des pilotes ODBC, via leur propre moteur de base de données.  Ils prennent également en charge des opérations de langage de définition de données \(DDL\), telles que l'ajout de tables via des classes au lieu de devoir appeler DAO vous\-même.  
  
> [!NOTE]
>  Le processus DFX \(DFX\) est très semblable à l'record field exchange \(bulk RFX\) dans les classes de base de données ODBC applications MFC \(`CDatabase`, `CRecordset`\).  Si vous incluez RFX, vous trouverez le DFX facile à utiliser.  
  
 Un objet d' `CDaoFieldExchange` fournit des informations de contexte nécessaires pour que le processus DFX ait lieu.  Les objets d'`CDaoFieldExchange` prennent en charge un certain nombre d'opérations, y compris les paramètres obligatoires et les données membres de champ et indicateurs de configuration de différentes sur les champs de l'enregistrement courant.  Les opérations de DFX sont exécutées sur les données membres de la classe de recordset des types définis par `enum`**type\_champ** dans `CDaoFieldExchange`.  Les valeurs possibles de **type\_champ** sont :  
  
-   **CDaoFieldExchange::outputColumn** pour les données membres de champ.  
  
-   **CDaoFieldExchange::param** pour les membres de données de type paramètre.  
  
 La fonction membre d' [IsValidOperation](../Topic/CDaoFieldExchange::IsValidOperation.md) est fournie pour écrire vos propres routines DFX personnalisées.  Vous utiliserez [SetFieldType](../Topic/CDaoFieldExchange::SetFieldType.md) fréquemment dans vos fonctions de [CDaoRecordset::DoFieldExchange](../Topic/CDaoRecordset::DoFieldExchange.md) .  Pour plus d'informations sur les fonctions globales de DFX, consultez [Fonctions de création de rapports d'échange des champs](../../mfc/reference/record-field-exchange-functions.md).  Pour plus d'informations sur les routines DFX personnalisées d'écriture de vos propres types de données, consultez [note technique 53](../../mfc/tn053-custom-dfx-routines-for-dao-database-classes.md).  
  
## Hiérarchie d'héritage  
 `CDaoFieldExchange`  
  
## Configuration requise  
 **Header:** afxdao.h  
  
## Voir aussi  
 [Graphique hiérarchique](../../mfc/hierarchy-chart.md)   
 [CDaoRecordset Class](../../mfc/reference/cdaorecordset-class.md)