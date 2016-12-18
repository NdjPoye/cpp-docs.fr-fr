---
title: "D&#233;termination du type d&#39;accesseur &#224; utiliser | Microsoft Docs"
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
  - "accesseurs (C++), types"
  - "jeux de lignes (C++), types de données"
ms.assetid: 22483dd2-f4e0-4dcb-8e4d-cd43a9c1a3db
caps.latest.revision: 7
caps.handback.revision: 7
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# D&#233;termination du type d&#39;accesseur &#224; utiliser
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Vous pouvez déterminer les types de données sur un jeu de lignes au moment de la compilation ou au moment de l'exécution.  
  
 Si vous devez déterminer les types de données au moment de la compilation, utilisez un accesseur statique \(tel que `CAccessor`\).  Vous pouvez déterminer les types de données manuellement ou en recourant à l'Assistant Consommateur OLE DB ATL.  
  
 Si vous devez déterminer les types de données au moment de l'exécution, utilisez un accesseur dynamique \(`CDynamicAccessor` ou ses enfants\) ou manuel \(`CManualAccessor`\).  Dans les deux cas, vous pouvez appeler `GetColumnInfo` sur le jeu de lignes pour retourner les informations relatives aux liaisons des colonnes, à partir desquelles vous pouvez déterminer les types.  
  
 Le tableau suivant récapitule les types d'accesseurs fournis dans les modèles du consommateur.  Chaque accesseur présente des avantages et des inconvénients.  Un type d'accesseur doit répondre à vos besoins, dans chaque cas.  
  
|Classes d'accesseurs|Liaison|Paramètre|Commentaire|  
|--------------------------|-------------|---------------|-----------------|  
|`CAccessor`|Créez un enregistrement d'utilisateur à l'aide des macros `COLUMN_ENTRY`.  Les macros lient des données membres de cet enregistrement à l'accesseur.  Une fois le jeu de lignes créé, les colonnes ne peuvent être déliées.|Oui, en utilisant une entrée de macro **PARAM\_MAP**.  Une fois liés, les paramètres ne peuvent pas être déliés.|L'accesseur le plus rapide en raison de la petite quantité de code utilisée.|  
|`CDynamicAccessor`|Automatique.|Non.|Utile si vous ne connaissez pas le type de données dans un jeu de lignes.|  
|`CDynamicParameterAccessor`|Automatique, mais peut être [substitué](../../data/oledb/overriding-a-dynamic-accessor.md).|Oui, si le fournisseur prend en charge `ICommandWithParameters`.  Les paramètres sont liés automatiquement.|Plus lent que `CDynamicAccessor` mais utile pour l'appel des procédures stockées génériques.|  
|**CDynamicStringAccessor\[A,W\]**|Automatique.|Non.|Récupère les données accessibles à partir du magasin de données en tant que données de type chaîne.|  
|`CManualAccessor`|Manuelle en utilisant `AddBindEntry`.|Manuels en utilisant `AddParameterEntry`.|Très rapide ; les paramètres et les colonnes sont liés une seule fois.  Vous déterminez le type de données à utiliser. \(Consultez l'exemple [DBVIEWER](http://msdn.microsoft.com/fr-fr/07620f99-c347-4d09-9ebc-2459e8049832).\) Exige davantage de code que `CDynamicAccessor` ou `CAccessor`.  Cela ressemble davantage à l'appel direct d'OLE DB.|  
|`CXMLAccessor`|Automatique.|Non.|Récupère les données accessibles à partir du magasin de données en tant que données de type chaîne, et les met en forme en tant que données XML.|  
  
## Voir aussi  
 [Utilisation des accesseurs](../../data/oledb/using-accessors.md)