---
title: "Macros et fonctions globales pour les mod&#232;les du consommateur OLE DB | Microsoft Docs"
ms.custom: ""
ms.date: "12/05/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "vc.templates.ole"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "macros, OLE DB (modèle du consommateur)"
  - "OLE DB (modèles du consommateur), macros"
ms.assetid: 8765eb7b-32dd-407c-bacf-8890ef959837
caps.latest.revision: 6
caps.handback.revision: 6
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Macros et fonctions globales pour les mod&#232;les du consommateur OLE DB
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Les modèles du consommateur OLE DB incluent les macros et les fonctions globales suivantes :  
  
### Fonctions globales  
  
|||  
|-|-|  
|[AtlTraceErrorRecords](../../data/oledb/atltraceerrorrecords.md)|Vidages des informations sur les enregistrements d'erreur OLE DB dans l'unité de vidage si une erreur est retournée.|  
  
### Macros de carte d'accesseur  
  
|||  
|-|-|  
|[BEGIN\_ACCESSOR](../../data/oledb/begin-accessor.md)|Marque le début d'une entrée d'accesseur.|  
|[BEGIN\_ACCESSOR\_MAP](../../data/oledb/begin-accessor-map.md)|Marque le début des entrées de mappage d'accesseur.|  
|[END\_ACCESSOR](../../data/oledb/end-accessor.md)|Marque la fin d'une entrée d'accesseur.|  
|[END\_ACCESSOR\_MAP](../../data/oledb/end-accessor-map.md)|Marque la fin des entrées de mappage d'accesseur.|  
  
### Macros de mappage de colonnes  
  
|||  
|-|-|  
|[BEGIN\_COLUMN\_MAP](../../data/oledb/begin-column-map.md)|Marque le début des entrées de mappage de colonnes dans la classe d'enregistrement de l'utilisateur.|  
|[BLOB\_ENTRY](../../data/oledb/blob-entry.md)|Permet de lier un grand objet binaire \(BLOB\).|  
|[BLOB\_ENTRY\_LENGTH](../../data/oledb/blob-entry-length.md)|Indique la longueur de la colonne de données BLOB.|  
|[BLOB\_ENTRY\_LENGTH\_STATUS](../../data/oledb/blob-entry-length-status.md)|Indique la longueur et l'état de la colonne de données BLOB.|  
|[BLOB\_ENTRY\_STATUS](../../data/oledb/blob-entry-status.md)|Signale l'état de la colonne de données BLOB.|  
|[BLOB\_NAME](../../data/oledb/blob-name.md)|Permet de lier un objet blob par son nom de colonne.|  
|[BLOB\_NAME\_LENGTH](../../data/oledb/blob-name-length.md)|Indique la longueur de la colonne de données BLOB.|  
|[BLOB\_NAME\_LENGTH\_STATUS](../../data/oledb/blob-name-length-status.md)|Indique la longueur et l'état de la colonne de données BLOB.|  
|[BLOB\_NAME\_STATUS](../../data/oledb/blob-name-status.md)|Signale l'état de la colonne de données BLOB.|  
|[BOOKMARK\_ENTRY](../../data/oledb/bookmark-entry.md)|Représente une entrée de signet sur l'ensemble de lignes.  Une entrée de signet est un type spécial de colonnes d'entrée.|  
|[COLUMN\_ENTRY](../../data/oledb/column-entry.md)|Représente une liaison à une colonne spécifique dans la base de données.|  
|[COLUMN\_ENTRY\_EX](../../data/oledb/column-entry-ex.md)|Représente une liaison à une colonne spécifique dans la base de données.  Prend en charge les paramètres `type`, *longueur*, *précision*, l'`scale`, et *état*.|  
|[COLUMN\_ENTRY\_LENGTH](../../data/oledb/column-entry-length.md)|Représente une liaison à une colonne spécifique dans la base de données.  Prend en charge la variable de *longueur*.|  
|[COLUMN\_ENTRY\_LENGTH\_STATUS](../../data/oledb/column-entry-length-status.md)|Représente une liaison à une colonne spécifique dans la base de données.  Prend en charge les paramètres d'*état* et de *longueur*.|  
|[COLUMN\_ENTRY\_PS](../../data/oledb/column-entry-ps.md)|Représente une liaison à une colonne spécifique dans la base de données.  Prend en charge les paramètres de *précision* et de `scale`.|  
|[COLUMN\_ENTRY\_PS\_LENGTH](../../data/oledb/column-entry-ps-length.md)|Représente une liaison à une colonne spécifique dans la base de données.  Prend en charge la variable de *longueur*, et les paramètres de *précision* et de `scale`.|  
|[COLUMN\_ENTRY\_PS\_LENGTH\_STATUS](../../data/oledb/column-entry-ps-length-status.md)|Représente une liaison à une colonne spécifique dans la base de données.  Prend en charge les variables *d'état* et de *longueur*, et les paramètres de *précision* et de `scale`.|  
|[COLUMN\_ENTRY\_PS\_STATUS](../../data/oledb/column-entry-ps-status.md)|Représente une liaison à une colonne spécifique dans la base de données.  Prend en charge la variable d' *état*, et les paramètres de *précision* et de `scale`.|  
|[COLUMN\_ENTRY\_STATUS](../../data/oledb/column-entry-status.md)|Représente une liaison à une colonne spécifique dans la base de données.  Prend en charge la variable d' *état*.|  
|[COLUMN\_ENTRY\_TYPE](../../data/oledb/column-entry-type.md)|Représente une liaison à une colonne spécifique dans la base de données.  Prend en charge le paramètre de `type`.|  
|[COLUMN\_ENTRY\_TYPE\_SIZE](../../data/oledb/column-entry-type-size.md)|Représente une liaison à une colonne spécifique dans la base de données.  Prend en charge les paramètres `type` et `size`.|  
|[COLUMN\_NAME](../../data/oledb/column-name.md)|Représente une liaison par nom à une colonne spécifique dans la base de données.|  
|[COLUMN\_NAME\_EX](../../data/oledb/column-name-ex.md)|Représente une liaison par nom à une colonne spécifique dans la base de données.  Prend en charge la spécification du type de données, la taille, la précision, l'échelle, la longueur de colonne, et de l'état de la colonne.|  
|[COLUMN\_NAME\_LENGTH](../../data/oledb/column-name-length.md)|Représente une liaison par nom à une colonne spécifique dans la base de données.  Prend en charge la spécification de la longueur de la colonne.|  
|[COLUMN\_NAME\_LENGTH\_STATUS](../../data/oledb/column-name-length-status.md)|Représente une liaison par nom à une colonne spécifique dans la base de données.  Prend en charge la spécification de la longueur et l'état de la colonne.|  
|[COLUMN\_NAME\_PS](../../data/oledb/column-name-ps.md)|Représente une liaison par nom à une colonne spécifique dans la base de données.  Prend en charge la spécification de précision et d'échelle.|  
|[COLUMN\_NAME\_PS\_LENGTH](../../data/oledb/column-name-ps-length.md)|Représente une liaison par nom à une colonne spécifique dans la base de données.  Prend en charge la spécification de la précision, l'échelle, et la longueur de la colonne.|  
|[COLUMN\_NAME\_PS\_LENGTH\_STATUS](../../data/oledb/column-name-ps-length-status.md)|Représente une liaison par nom à une colonne spécifique dans la base de données.  Prend en charge la spécification de la précision, l'échelle, la longueur de colonne, et de l'état de la colonne.|  
|[COLUMN\_NAME\_PS\_STATUS](../../data/oledb/column-name-ps-status.md)|Représente une liaison par nom à une colonne spécifique dans la base de données.  Prend en charge la spécification de la précision, l'échelle, et l'état de la colonne.|  
|[COLUMN\_NAME\_STATUS](../../data/oledb/column-name-status.md)|Représente une liaison par nom à une colonne spécifique dans la base de données.  Prend en charge la spécification de l'état de la colonne.|  
|[COLUMN\_NAME\_TYPE](../../data/oledb/column-name-type.md)|Représente une liaison par nom à une colonne spécifique dans la base de données.  Prend en charge la spécification du type de données.|  
|[COLUMN\_NAME\_TYPE\_PS](../../data/oledb/column-name-type-ps.md)|Représente une liaison par nom à une colonne spécifique dans la base de données.  Prend en charge la spécification du type de données, de la précision, et de l'échelle.|  
|[COLUMN\_NAME\_TYPE\_SIZE](../../data/oledb/column-name-type-size.md)|Représente une liaison par nom à une colonne spécifique dans la base de données.  Prend en charge la spécification du type de données et de la taille.|  
|[COLUMN\_NAME\_TYPE\_STATUS](../../data/oledb/column-name-type-status.md)|Représente une liaison par nom à une colonne spécifique dans la base de données.  Prend en charge la spécification de l'état et du type de données de la colonne.|  
|[END\_COLUMN\_MAP](../../data/oledb/end-column-map.md)|Marque la fin des entrées de mappage de colonnes.|  
  
### macros de commande  
  
|||  
|-|-|  
|[DEFINE\_COMMAND](../../data/oledb/define-command.md)|Spécifie la commande qui sera utilisée pour créer l'ensemble des lignes lorsque vous utilisez la classe [CCommand](../../data/oledb/ccommand-class.md).  Accepte uniquement les types de chaîne correspondant au type d'application spécifié \(ANSI ou Unicode\).  Il est recommandé d'utiliser [DEFINE\_COMMAND\_EX](../../data/oledb/define-command-ex.md) au lieu de `DEFINE_COMMAND`.|  
|[DEFINE\_COMMAND\_EX](../../data/oledb/define-command-ex.md)|Spécifie la commande qui sera utilisée pour créer l'ensemble des lignes lorsque vous utilisez la classe [CCommand](../../data/oledb/ccommand-class.md).  Prend en charge les applications ANSI et Unicode.|  
  
### Macros de mappage de paramètre  
  
|||  
|-|-|  
|[BEGIN\_PARAM\_MAP](../../data/oledb/begin-param-map.md)|Marque le début des entrées de mappage de paramètres dans la classe d'enregistrement de l'utilisateur.|  
|[END\_PARAM\_MAP](../../data/oledb/end-param-map.md)|Marque la fin des entrées de mappage de paramètres.|  
|[SET\_PARAM\_TYPE](../../data/oledb/set-param-type.md)|Spécifie les macros `COLUMN_ENTRY` qui suivent la macro `SET_PARAM_TYPE` en tant qu'entrée, sortie, ou entrée\/sortie.|  
  
## Voir aussi  
 [Modèles du consommateur OLE DB](../../data/oledb/ole-db-consumer-templates-cpp.md)   
 [Modèles du consommateur OLE DB](../../data/oledb/ole-db-consumer-templates-cpp.md)   
 [Référence des modèles du consommateur OLE DB](../../data/oledb/ole-db-consumer-templates-reference.md)