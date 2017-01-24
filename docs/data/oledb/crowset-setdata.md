---
title: "CRowset::SetData | Microsoft Docs"
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
  - "ATL.CRowset<TAccessor>.SetData"
  - "SetData"
  - "ATL::CRowset::SetData"
  - "CRowset<TAccessor>.SetData"
  - "CRowset::SetData"
  - "ATL.CRowset.SetData"
  - "CRowset.SetData"
  - "CRowset<TAccessor>::SetData"
  - "ATL::CRowset<TAccessor>::SetData"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "SetData (méthode)"
ms.assetid: 68125142-8510-4132-9393-e39efd39c784
caps.latest.revision: 9
caps.handback.revision: 9
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# CRowset::SetData
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Définit les valeurs de données dans une ou plusieurs colonnes d'une ligne.  
  
## Syntaxe  
  
```  
  
      HRESULT SetData( ) const throw( );   
HRESULT SetData(  
   int nAccessor   
) const throw( );  
```  
  
#### Paramètres  
 `nAccessor`  
 \[in\] L'index de l'accesseur à utiliser pour accéder aux données.  
  
## Valeur de retour  
 Un `HRESULT` standard.  
  
## Notes  
 Pour la forme `SetData` qui n'accepte aucun argument, tous les accesseurs sont utilisés pour mettre à jour.  Vous appelez en général **SetData** pour définir des valeurs de données à la suite dans les colonnes, puis appelez [Mettre à jour](../../data/oledb/crowset-update.md) pour transmettre ces modifications.  
  
 Cette méthode requiert l'interface facultative `IRowsetChange`, qui peut ne pas être prise en charge chez tous les fournisseurs ; dans ce cas, la méthode retourne **E\_NOINTERFACE**.  Vous devez également définir **DBPROP\_IRowsetChange** sur `VARIANT_TRUE` avant d'appeler **Ouvrir** sur la table ou la commande contenant l'ensemble de lignes.  
  
 L'opération de paramètre peut échouer si une ou plusieurs colonnes n'est pas activé en écriture.  Modifiez le mappage du curseur pour remédier à cette situation.  
  
## Configuration requise  
 **En\-tête :** atldbcli.h  
  
## Voir aussi  
 [CRowset, classe](../../data/oledb/crowset-class.md)   
 [CRowset::Update](../../data/oledb/crowset-update.md)