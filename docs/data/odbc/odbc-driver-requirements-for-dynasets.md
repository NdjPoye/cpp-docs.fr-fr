---
title: "Pilote ODBC requis pour les feuilles de r&#233;ponse dynamiques | Microsoft Docs"
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
  - "pilotes, pour les dynasets"
  - "pilotes, ODBC"
  - "dynasets"
  - "ODBC (pilotes), dynasets"
  - "ODBC (recordsets), dynasets"
  - "recordsets, dynasets"
ms.assetid: 585cc67b-4d92-404b-9903-d769cd17badc
caps.latest.revision: 7
caps.handback.revision: 7
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Pilote ODBC requis pour les feuilles de r&#233;ponse dynamiques
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Dans les classes de bases de données ODBC MFC, les feuilles de réponse dynamiques sont des recordsets possédant des propriétés dynamiques ; elles restent en quelque sorte synchronisées avec les sources de données.  Les feuilles de réponse dynamiques MFC \(mais pas les recordsets à défilement en avant\) nécessitent un pilote ODBC conforme au niveau 2 d'API.  Si le pilote de votre [source de données](../../data/odbc/data-source-odbc.md) est conforme au niveau 1 du jeu d'API, vous pouvez toujours utiliser les instantanés modifiables et en lecture seule ainsi que les recordsets à défilement en avant, mais pas les feuilles de réponse dynamiques.  Cependant, un pilote de niveau 1 peut prendre en charge les feuilles de réponse dynamiques s'il prend également en charge l'extraction étendue et les curseurs commandés par un keyset.  
  
 Dans la terminologie ODBC, les feuilles de réponse dynamiques et les instantanés sont désignés par le terme « curseur ».  Un curseur est un mécanisme utilisé pour assurer le suivi de son emplacement dans un recordset.  Pour plus d'informations sur les pilotes requis pour les feuilles de réponse dynamiques, consultez [Feuille de réponse dynamique](../../data/odbc/dynaset.md).  Pour plus d'informations sur les curseurs, consultez le kit de développement [ODBC \(Open Database Connectivity\)](https://msdn.microsoft.com/en-us/library/ms710252.aspx) SDK dans la documentation MSDN.  
  
> [!NOTE]
>  Pour les recordsets modifiables, votre pilote ODBC doit prendre en charge les instructions de mise à jour positionnée ou la fonction API ODBC **::SQLSetPos**.  Si ces deux éléments sont pris en charge, MFC utilise **::SQLSetPos** pour une plus grande efficacité.  Pour les instantanés, vous pouvez aussi utiliser la bibliothèque de curseurs, qui fournit la prise en charge nécessaire pour les instantanés modifiables \(curseurs statiques et instructions de mise à jour positionnée\).  
  
## Voir aussi  
 [Éléments fondamentaux relatifs à ODBC](../../data/odbc/odbc-basics.md)