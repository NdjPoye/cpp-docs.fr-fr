---
title: "paire (STL/CLR) | Microsoft Docs"
ms.custom: ""
ms.date: "12/05/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "cliext::pair"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "classe pair [STL/CLR]"
ms.assetid: 3326b4d9-a52a-49e5-8103-9aa5e8b352de
caps.latest.revision: 5
caps.handback.revision: 5
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# paire (STL/CLR)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

La classe du modèle décrit un objet qui encapsule une paire de valeurs.  
  
## Syntaxe  
  
```  
template<typename Value1,  
    typename Value2>  
    ref class pair;  
```  
  
#### Paramètres  
 Value1  
 Le type de la première valeur encapsulée.  
  
 Value2  
 Le type de la seconde valeur encapsulée.  
  
## Membres  
  
|Définition de type|Description|  
|------------------------|-----------------|  
|[pair::first\_type](../dotnet/pair-first-type-stl-clr.md)|Type de la première valeur encapsulée.|  
|[pair::second\_type](../dotnet/pair-second-type-stl-clr.md)|Type de la deuxième valeur encapsulée.|  
  
|Objet membre|Description|  
|------------------|-----------------|  
|[pair::first](../dotnet/pair-first-stl-clr.md)|Première valeur stockée.|  
|[pair::second](../dotnet/pair-second-stl-clr.md)|Seconde valeur stockée.|  
  
|Méthodes|Description|  
|--------------|-----------------|  
|[pair::pair](../dotnet/pair-pair-stl-clr.md)|Construit un objet de paire.|  
|[pair::swap](../dotnet/pair-swap-stl-clr.md)|Échange le contenu de deux paires.|  
  
|Opérateur|Description|  
|---------------|-----------------|  
|[pair::operator\=](../dotnet/pair-operator-assign-stl-clr.md)|Remplace les paires de valeurs stockées.|  
  
## Notes  
 L'objet enregistre une paire de valeurs.  Vous utilisez cette classe de modèle pour combiner deux valeurs dans un objet.  Notez que `cliext::pair` \(décrit ici\) stocke uniquement des types managés ; pour enregistrer une paire de types non managés, utilisez `std::pair`, déclaré dans `<utility>`.  
  
## Configuration requise  
 **En\-tête :** \<cliext\/utility\>  
  
 **Espace de noms :** cliext  
  
## Voir aussi  
 [make\_pair](../dotnet/make-pair-stl-clr.md)