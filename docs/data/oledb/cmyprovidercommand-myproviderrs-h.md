---
title: "CMyProviderCommand (MyProviderRS.H) | Microsoft Docs"
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
  - "cmyprovidercommand"
  - ""myproviderrs.h""
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CMyProviderCommand (classe dans MyProviderRS.H)"
  - "fournisseurs OLE DB, fichiers générés par l'Assistant"
ms.assetid: b30b956e-cc91-4cf5-9fe6-f8b1ce9cc2a5
caps.latest.revision: 7
caps.handback.revision: 7
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# CMyProviderCommand (MyProviderRS.H)
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

La classe `CMyProviderCommand` est l'implémentation de l'objet command du fournisseur.  Elle assure l'implémentation pour les interfaces `IAccessor`, `ICommandText` et **ICommandProperties**.  L'interface `IAccessor` est la même que celle du jeu de lignes.  L'objet command utilise l'accesseur pour spécifier les liaisons des paramètres.  L'objet rowset les utilise pour spécifier les liaisons des colonnes de sortie.  L'interface `ICommandText` offre un moyen pratique pour la spécification textuelle d'une commande.  Cet exemple utilise l'interface `ICommandText` ultérieurement quand il ajoutera un code personnalisé ; il substitue également la méthode `ICommand::Execute`.  L'interface **ICommandProperties** gère toutes les propriétés des objets command et rowset.  
  
```  
// CMyProviderCommand  
class ATL_NO_VTABLE CMyProviderCommand :   
class ATL_NO_VTABLE CMyProviderCommand :   
   public CComObjectRootEx<CComSingleThreadModel>,  
   public IAccessorImpl<CMyProviderCommand>,  
   public ICommandTextImpl<CMyProviderCommand>,  
   public ICommandPropertiesImpl<CMyProviderCommand>,  
   public IObjectWithSiteImpl<CMyProviderCommand>,  
   public IConvertTypeImpl<CMyProviderCommand>,  
   public IColumnsInfoImpl<CMyProviderCommand>  
```  
  
 L'interface `IAccessor` gère toutes les liaisons utilisées dans les commandes et les jeux de lignes.  Le consommateur appelle **IAccessor::CreateAccessor** à l'aide d'un tableau de structures **DBBINDING**.  Chaque structure **DBBINDING** contient les informations indiquant comment les liaisons des colonnes doivent être gérées \(type et longueur, par exemple\).  Le fournisseur reçoit les structures puis détermine comment les données doivent être transférées et si des conversions sont nécessaires.  L'interface `IAccessor` est utilisée dans l'objet command pour gérer éventuellement les paramètres de la commande.  
  
 L'objet command assure également une implémentation de l'interface `IColumnsInfo`.  OLE DB requiert l'interface `IColumnsInfo`.  Cette interface permet au consommateur de récupérer des informations sur les paramètres à partir de la commande.  L'objet rowset utilise l'interface `IColumnsInfo` pour retourner au fournisseur des informations sur les colonnes de sortie.  
  
 Le fournisseur contient également une interface appelée `IObjectWithSite`.  L'interface `IObjectWithSite` a été implémentée dans ATL 2.0 et permet à l'implémenteur de passer des informations sur lui\-même à son enfant.  L'objet command utilise les informations de l'interface `IObjectWithSite` pour indiquer aux objets rowset éventuellement générés qui les a créés.  
  
## Voir aussi  
 [Fichiers générés par l'Assistant Fournisseur](../../data/oledb/provider-wizard-generated-files.md)