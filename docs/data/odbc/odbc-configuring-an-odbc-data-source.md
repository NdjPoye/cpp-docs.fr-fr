---
title: "ODBC&#160;: configuration d&#39;une source de donn&#233;es ODBC | Microsoft Docs"
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
  - "configurer les sources de données ODBC"
  - "ODBC (connexions), configurer"
  - "sources de données ODBC, configurer"
ms.assetid: 1cd03e6a-8d59-4eca-a8c6-1010582d5e67
caps.latest.revision: 7
caps.handback.revision: 7
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# ODBC&#160;: configuration d&#39;une source de donn&#233;es ODBC
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Pour utiliser une [source de données](../../data/odbc/data-source-odbc.md) avec une application que vous avez développée, vous devez utiliser l'Administrateur ODBC pour la configurer.  L'Administrateur ODBC assure le suivi des sources de données disponibles et des informations relatives à leurs connexions dans le Registre Windows.  Utilisez l'Administrateur ODBC pour ajouter, modifier et supprimer les sources de données dans la boîte de dialogue **Sources de données** ainsi que pour ajouter et supprimer des pilotes ODBC.  
  
> [!NOTE]
>  Ces informations s'appliquent lorsque vous utilisez les classes DAO \(Data Access Object\) MFC pour accéder à ODBC, ainsi que lorsque vous utilisez les classes ODBC MFC.  
  
 L'Administrateur ODBC est automatiquement installé avec la prise en charge de base de données de la bibliothèque MFC \(Microsoft Foundation Classes\).  Pour plus d'informations sur le programme d'administration ODBC, consultez [Administrateur ODBC](../../data/odbc/odbc-administrator.md) et le système d'aide en ligne ODBC API Reference.  
  
 La [Technical Note 48](../../mfc/tn048-writing-odbc-setup-and-administration-programs.md) explique comment écrire des programmes d'installation et d'administration ODBC pour les applications de base de données MFC.  
  
## Voir aussi  
 [Éléments fondamentaux relatifs à ODBC](../../data/odbc/odbc-basics.md)   
 [ODBC : appel direct de fonctions API ODBC](../../data/odbc/odbc-calling-odbc-api-functions-directly.md)