---
title: "CFieldExchange Class | Microsoft Docs"
ms.custom: ""
ms.date: "12/05/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "CFieldExchange"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CFieldExchange class"
  - "types de données (C++), personnalisé"
  - "enum FieldType"
  - "enum FieldType, CFieldExchange"
  - "FieldType enumeration"
  - "RFX (record field exchange) [C++]"
  - "RFX (record field exchange) [C++], classes for"
ms.assetid: 24c5c0b3-06a6-430e-9b6f-005a2c65e29f
caps.latest.revision: 24
caps.handback.revision: 14
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# CFieldExchange Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Prend en charge les routines d'enregistrement de l'échange de RFX \(record field exchange\) et le mécanisme RFX en bloc \(bulk RFX\) utilisés par les classes de base de données.  
  
## Syntaxe  
  
```  
  
class CFieldExchange  
  
```  
  
## Membres  
  
### Méthodes publiques  
  
|Nom|Description|  
|---------|-----------------|  
|[CFieldExchange::IsFieldType](../Topic/CFieldExchange::IsFieldType.md)|Retourne une valeur différente de zéro si l'opération en cours est appropriée pour le type de champ qui est mis à jour.|  
|[CFieldExchange::SetFieldType](../Topic/CFieldExchange::SetFieldType.md)|Spécifie le type de donnée membre du recordset — colonne ou paramètre — représenté par tous les appels suivants à RFX fonctionne jusqu'à l'appel suivant à `SetFieldType`.|  
  
## Notes  
 `CFieldExchange` n'a pas de classe de base.  
  
 Utilisez cette classe si vous écrivez des routines d'échange de données pour les types de données personnalisés ou lorsque vous implémentez l'extraction de lignes en bloc ; sinon, vous n'utiliserez pas directement cette classe.  RFX et données d'échange en bloc RFX entre les données membres de champ de l'objet recordset et les champs correspondants de l'enregistrement en cours sur la source de données.  
  
> [!NOTE]
>  Si vous utilisez DAO \(DAO\) classe plutôt que les classes ODBC \(Open Database Connectivity\), utilisez la classe [CDaoFieldExchange](../../mfc/reference/cdaofieldexchange-class.md) à la place.  Pour plus d'informations, consultez l'article [présentation : Programmation de bases de données](../../data/data-access-programming-mfc-atl.md).  
  
 Un objet d' `CFieldExchange` fournit des informations de contexte nécessaires pour que l'record field exchange ou RFX en bloc n'ait lieu.  Les objets d'`CFieldExchange` prennent en charge un certain nombre d'opérations, y compris les paramètres obligatoires et les données membres de champ et indicateurs de configuration de différentes sur les champs de l'enregistrement courant.  RFX et les opérations en bloc RFX sont exécutés sur des données membres de la classe de recordset des types définis par `enum`**type\_champ** dans `CFieldExchange`.  Les valeurs possibles de **type\_champ** sont :  
  
-   **CFieldExchange::outputColumn** pour les données membres de champ.  
  
-   **CFieldExchange::inputParam** ou **CFieldExchange::param** pour les membres de données de type paramètre d'entrée.  
  
-   **CFieldExchange::outputParam** pour les membres de données de type paramètre de sortie.  
  
-   **CFieldExchange::inoutParam** pour les membres de données de type paramètre d'entrée\/sortie.  
  
 La plupart des fonctions membres et les données membres de la classe sont fournies pour écrire vos propres routines de le personnalisé RFX.  Vous utiliserez `SetFieldType` fréquemment.  Pour plus d'informations, consultez les articles [Record field exchange \(RFX\)](../../data/odbc/record-field-exchange-rfx.md) et [recordset \(ODBC\)](../../data/odbc/recordset-odbc.md).  Pour plus d'informations sur l'extraction de lignes en bloc, consultez l'article [recordset : Extraction globale d'enregistrements \(ODBC\)](../../data/odbc/recordset-fetching-records-in-bulk-odbc.md).  Pour plus d'informations sur les fonctions globales RFX et RFX en bloc, consultez l' [Enregistrez les fonctions d'échange des champs](../../mfc/reference/record-field-exchange-functions.md) dans la section de macro MFC et Globals de cette référence.  
  
## Hiérarchie d'héritage  
 `CFieldExchange`  
  
## Configuration requise  
 **Header:** afxdb.h  
  
## Voir aussi  
 [Graphique hiérarchique](../../mfc/hierarchy-chart.md)   
 [CRecordset Class](../../mfc/reference/crecordset-class.md)