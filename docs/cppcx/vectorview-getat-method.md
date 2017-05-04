---
title: "VectorView::GetAt (m&#233;thode) | Microsoft Docs"
ms.custom: ""
ms.date: "12/14/2016"
ms.prod: "windows-client-threshold"
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
f1_keywords: 
  - "collection/Platform::Collections::VectorView::GetAt"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "VectorView::GetAt (méthode)"
ms.assetid: 01c5feda-2a97-4429-ae15-4aced96ce332
caps.latest.revision: 3
author: "ghogen"
ms.author: "ghogen"
manager: "ghogen"
---
# VectorView::GetAt (m&#233;thode)
Récupère l'élément du VectorView actuel qui est indiqué par l'index spécifié.  
  
## Syntaxe  
  
```  
  
T GetAt(  
   UInt32 index  
);  
```  
  
#### Paramètres  
 `index`  
 Entier non signé de base zéro qui spécifie un élément particulier dans l’objet VectorView.  
  
## Valeur de retour  
 Élément spécifié par le paramètre `index`. Le type d’élément est spécifié par le paramètre de modèle VectorView, *T*.  
  
## Configuration requise  
 **En\-tête :** collection.h  
  
 **Espace de noms :** Platform::Collections  
  
## Voir aussi  
 [VectorView Class](http://msdn.microsoft.com/fr-fr/79697692-ae58-40e0-958f-cf1be6347994)