---
title: "CDataSource, classe | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "ATL.CDataSource"
  - "ATL::CDataSource"
  - "CDataSource"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CDataSource (classe)"
ms.assetid: 99bf862c-9d5c-4117-9501-aa0e2672085c
caps.latest.revision: 12
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 12
---
# CDataSource, classe
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Correspond à un objet de source de données OLE DB, qui représente une connexion par un fournisseur à une source de données.  
  
## Syntaxe  
  
```  
class CDataSource  
```  
  
## Membres  
  
### Méthodes  
  
|||  
|-|-|  
|[Fermer](../../data/oledb/cdatasource-close.md)|Ferme la connexion.|  
|[GetInitializationString](../../data/oledb/cdatasource-getinitializationstring.md)|Récupère la chaîne d'initialisation de la source de données qui est actuellement ouverte.|  
|[ObtenirPropriétés](../../data/oledb/cdatasource-getproperties.md)|Obtient les valeurs des propriétés définies actuellement pour la source de données connectée.|  
|[ObtenirPropriété](../../data/oledb/cdatasource-getproperty.md)|Obtient la valeur d'une propriété actuellement définie pour la source de données connectée.|  
|[Ouvrez .](../../data/oledb/cdatasource-open.md)|Crée une connexion à un fournisseur \(source de données\) à **CLSID**, **ProgID**, ou un moniker de `CEnumerator` fourni par l'appelant.|  
|[OuvrirParNomFichier](../../data/oledb/cdatasource-openfromfilename.md)|Ouvre une source de données d'un fichier spécifié par le nom de fichier fourni par l'utilisateur.|  
|[OuvrirParInitialisationCaractère](../../data/oledb/cdatasource-openfrominitializationstring.md)|Ouvre la source de données spécifiée par une chaîne d'initialisation.|  
|[OuvreAvecNomFichierSansFaute](../../data/oledb/cdatasource-openwithpromptfilename.md)|Permet à l'utilisateur de sélectionner un fichier de liaison de données créé précédemment pour ouvrir la source de données correspondante.|  
|[OuvrirAvecComposantService](../../data/oledb/cdatasource-openwithservicecomponents.md)|Ouvre un objet source de données à l'aide de la boîte de dialogue liaison de données.|  
  
## Notes  
 Une ou plusieurs sessions de base de données peuvent être créées pour une connexion unique.  Ces sessions sont représentées par `CSession`.  Vous devez appeler [CDataSource::Open](../../data/oledb/cdatasource-open.md) pour ouvrir la connexion avant de créer une session avec `CSession::Open`.  
  
 Pour obtenir un exemple de la façon d'utiliser le contrôle `CDataSource`, consultez [CatDB](../../top/visual-cpp-samples.md).  
  
## Configuration requise  
 **En\-tête :** atldbcli.h  
  
## Voir aussi  
 [Modèles du consommateur OLE DB](../../data/oledb/ole-db-consumer-templates-cpp.md)   
 [Référence des modèles du consommateur OLE DB](../../data/oledb/ole-db-consumer-templates-reference.md)