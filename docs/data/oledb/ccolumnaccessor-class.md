---
title: "CColumnAccessor, classe | Microsoft Docs"
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
  - "CColumnAccessor"
  - "ATL::CColumnAccessor"
  - "ATL.CColumnAccessor"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CColumnAccessor (classe)"
ms.assetid: 6ce1e67f-6a20-490d-9326-c168b43eee7e
caps.latest.revision: 8
caps.handback.revision: 8
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# CColumnAccessor, classe
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

génère du code de consommation qui est injecté.  
  
## Syntaxe  
  
```  
class CColumnAccessor : public CAccessorBase  
```  
  
## Notes  
 Dans le code injecté, chaque colonne est liée comme accesseur distinct.  Vous devez savoir que cette classe est utilisée dans le code injecté \(par exemple, vous pouvez le constater le débogage\), mais en général ne devez jamais utiliser directement il ses méthodes.  
  
 `CColumnAccessor` implémente les méthodes stub suivantes, chacune qui correspondent aux fonctionnalités des autres méthodes de la classe d'accesseur :  
  
-   `CColumnAccessor` le constructeur ; les instanciés et initialise l'objet `CColumnAccessor`.  
  
-   `CreateAccessor` Attribue la mémoire pour les structures de colonnes de lien et initialise les colonnes des données des membres.  
  
-   **BindColumns** Lie les colonnes aux accesseurs.  
  
-   **SetParameterBuffer** alloue les mémoires tampons de paramètres.  
  
-   `AddParameter` ajoute une entrée de paramètres aux structures d'entrée de paramètre.  
  
-   **HasOutputColumns** détermine si l'accesseur a des colonnes de sortie  
  
-   **HasParameters** détermine si l'accesseur a des paramètres.  
  
-   `BindParameters` lie les paramètres créés aux colonnes.  
  
## Configuration requise  
 **En\-tête :** : atldbcli.h  
  
## Voir aussi  
 [Modèles du consommateur OLE DB](../../data/oledb/ole-db-consumer-templates-cpp.md)   
 [Référence des modèles du consommateur OLE DB](../../data/oledb/ole-db-consumer-templates-reference.md)