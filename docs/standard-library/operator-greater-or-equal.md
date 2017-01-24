---
title: "&gt;= (op&#233;rateur) | Microsoft Docs"
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
  - "operator>="
  - "std::>="
  - "std.operator>="
  - ">="
  - "std.>="
  - "std::operator>="
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - ">= (opérateur), comparer des objets spécifiques"
  - "(opérateur) >="
  - ">= (opérateur)"
ms.assetid: 14fbebf5-8b75-4afa-a51b-3112d31c07cf
caps.latest.revision: 9
caps.handback.revision: 8
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# &gt;= (op&#233;rateur)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

> [!NOTE]
>  Cette rubrique est dans la documentation Visual C\+\+ comme exemple non fonctionnel de conteneurs utilisés dans la bibliothèque C\+\+ de base.  Pour plus d'informations, consultez [STL Containers](../standard-library/stl-containers.md).  
  
 Surcharge **operator\>\=** pour comparer deux objets de classe de modèle [Conteneur](../standard-library/sample-container-class.md).  
  
## Syntaxe  
  
```  
  
   template<class Ty>  
bool operator>=(  
   const Container <Ty>& _Left,  
   const Container <Ty>& _Right  
);  
```  
  
## Valeur de retour  
 Retourne **\!**\(\_*Left* \< \_*Right*\).  
  
## Voir aussi  
 [\<sample container\>](../standard-library/sample-container.md)