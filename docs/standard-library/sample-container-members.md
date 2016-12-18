---
title: "Exemple de conteneurs, membres | Microsoft Docs"
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
  - "classes de conteneur"
ms.assetid: dc5a1998-a31b-4adf-b888-8abe5b87a4e0
caps.latest.revision: 9
caps.handback.revision: 8
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# Exemple de conteneurs, membres
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

> [!NOTE]
>  Cette rubrique est dans la documentation Visual C\+\+ comme exemple fonctionnel de conteneurs utilisés dans la bibliothèque C\+\+ standard.  Pour plus d'informations, consultez l'[Conteneurs STL de](../standard-library/stl-containers.md).  
  
## Référence  
  
## Typedef  
  
|||  
|-|-|  
|[const\_iterator](../standard-library/container-class-const-iterator.md)|Décrit un objet pouvant servir d'itérateur constant à la séquence contrôlée.|  
|[const\_reference](../standard-library/container-class-const-reference.md)|Décrit un objet qui peut servir de référence constante à un élément de la séquence contrôlée.|  
|[const\_reverse\_iterator](../standard-library/container-class-const-reverse-iterator.md)|Décrit un objet pouvant servir d'itérateur inverse constant à la séquence contrôlée.|  
|[difference\_type](../standard-library/container-class-difference-type.md)|Décrit un objet qui peut représenter la différence entre les adresses de deux éléments quelconques de la séquence contrôlée.|  
|[itérateur](../standard-library/container-class-iterator.md)|Décrit un objet pouvant servir d'itérateur situé à la séquence contrôlée.|  
|[référence](../standard-library/container-class-reference.md)|Décrit un objet qui peut servir de référence à un élément de la séquence contrôlée.|  
|[reverse\_iterator](../standard-library/container-class-reverse-iterator.md)|Décrit un objet pouvant servir d'itérateur inverse à la séquence contrôlée.|  
|[type\_taille](../standard-library/container-class-size-type.md)|Décrit un objet qui peut représenter la longueur de n'importe quelle séquence contrôlée.|  
|[type valeur](../standard-library/container-class-value-type.md)|Agit d'un synonyme pour le paramètre **Ty**de modèle.|  
  
## Fonctions membres  
  
|||  
|-|-|  
|[begin](../standard-library/container-class-begin.md)|Retourne un itérateur qui pointe vers le premier élément dans la séquence \(ou seulement au delà de la fin d'une séquence vide.|  
|[clear](../standard-library/container-class-clear.md)|Appelle [effacement](../standard-library/container-class-erase.md)\( [démarrez](../standard-library/container-class-begin.md), [end](../standard-library/container-class-end.md)\).|  
|[empty](../standard-library/container-class-empty.md)|Retourne **true** pour une séquence vide contrôlée.|  
|[end](../standard-library/container-class-end.md)|Retourne un itérateur qui pointe uniquement au delà de la fin de la séquence.|  
|[effacer](../standard-library/container-class-erase.md)|Efface un élément.|  
|[max\_size](../standard-library/container-class-max-size.md)|Retourne la longueur de la plus longue séquence que l'objet peut contrôler, dans le temps fixe quelle que soit la longueur de la séquence contrôlée.|  
|[rbegin](../standard-library/container-class-rbegin.md)|Retourne un itérateur inverse qui pointe uniquement au delà de la fin de la séquence contrôlée, qui indique le début de la séquence d'annulation.|  
|[rend](../standard-library/container-class-rend.md)|La fonction retourne un membre itérateur inverse qui pointe vers le premier élément dans la séquence \(ou seulement au delà de la fin d'une séquence vide\), qui indique la fin de la séquence d'annulation.|  
|[taille](../standard-library/container-class-size.md)|Retourne la longueur de la séquence contrôlée, dans le temps fixe quelle que soit la longueur de la séquence contrôlée.|  
|[échange](../standard-library/container-class-swap.md)|Habite les séquences réorganisées entre **\*this** et `_Right`.|