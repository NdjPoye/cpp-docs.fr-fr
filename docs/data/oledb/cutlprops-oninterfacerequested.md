---
title: "CUtlProps::OnInterfaceRequested | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "CUtlProps"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "OnInterfaceRequested (méthode)"
ms.assetid: a5e1a879-cff3-4e01-b902-2249a152984f
caps.latest.revision: 8
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 8
---
# CUtlProps::OnInterfaceRequested
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Les demandes des gestionnaires pour une interface facultative lorsqu'un consommateur appelle une méthode sur une de la création d'objets interfaces.  
  
## Syntaxe  
  
```  
  
      virtual HRESULT CUtlPropsBase::OnInterfaceRequested(  
   REFIID riid  
);  
```  
  
#### Paramètres  
 `riid`  
 \[in\] L'IID pour l'interface requis.  Pour plus d'informations, consultez la description du paramètre de `riid` de `ICommand::Execute` dans *OLE DB guide de référence du programmeur* \(dans *MDAC SDK*  
  
## Notes  
 **SurInterfaceRequis** traite les demandes du consommateur d'une interface facultative lorsqu'un consommateur appelle une méthode sur l'une des interfaces de création d'objets \(telles que **IDBCreerSession**, **IDBCreerCommande**, `IOpenRowset`, ou `ICommand`\).  Il définit la propriété correspondante OLE DB pour l'interface demandée.  Par exemple, si le consommateur demande **IID\_IRowsetLocate**, **SurInterfaceRequise** définit l'interface de **DBPROP\_IRowsetLocate**.  Gère le maintien approprié lors de la création de l'ensemble de lignes.  
  
 Cette méthode est appelée lorsque le consommateur appelle **IOpenRowset::OpenRowset** ou `ICommand::Execute`.  
  
 Si un consommateur ouvre un objet et demande une interface facultative, le fournisseur doit définir la propriété associée à cette interface à `VARIANT_TRUE`.  Pour permettre le traitement spécifique à, **OnInterfaceRequested** est appelée avant la méthode de **Exécuter** du fournisseur appelée.  Par défaut, **SurInterfaceRequise** gère les interfaces suivantes :  
  
-   `IRowsetLocate`  
  
-   `IRowsetChange`  
  
-   `IRowsetUpdate`  
  
-   **IConnectionPointContainer**  
  
-   `IRowsetScroll`  
  
 Si vous souhaitez gérer d'autres interfaces, remplacez cette fonction dans votre source de données, la session, la commande, ou la classe d'ensemble du traitement des fonctions.  Le fichier doit autoriser des interfaces régulières définies\/obtenir des propriétés pour s'assurer que la définition des propriétés définit également les propriétés chaînées \(voir [SurChangementPropriétés](../../data/oledb/cutlprops-onpropertychanged.md)\).  
  
## Configuration requise  
 **En\-tête :** atldb.h  
  
## Voir aussi  
 [CUtlProps, classe](../../data/oledb/cutlprops-class.md)