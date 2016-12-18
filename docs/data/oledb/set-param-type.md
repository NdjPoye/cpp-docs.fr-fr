---
title: "SET_PARAM_TYPE | Microsoft Docs"
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
  - "SET_PARAM_TYPE"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "SET_PARAM_TYPE (macro)"
ms.assetid: 85979070-2d55-4c67-94b1-9b9058babc59
caps.latest.revision: 9
caps.handback.revision: 9
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# SET_PARAM_TYPE
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Spécifie les macros `COLUMN_ENTRY` qui suivent l’entrée, la sortie ou l’entrée\/sortie de macro `SET_PARAM_TYPE`.  
  
## Syntaxe  
  
```  
  
SET_PARAM_TYPE(  
type  
 )  
  
```  
  
#### Paramètres  
 `type`  
 \[in\] Type à définir pour le paramètre.  
  
## Notes  
 Les fournisseurs prennent en charge uniquement les types d’entrée\/sortie de paramètres qui sont pris en charge par la source de données sous\-jacente. Le type est une combinaison d’une ou plusieurs valeurs **DBPARAMIO** \(voir [Structures DBBINDING](https://msdn.microsoft.com/en-us/library/ms716845.aspx) dans les *Informations de référence du programmeur OLE DB*\) :  
  
-   **DBPARAMIO\_NOTPARAM** L’accesseur n’a aucun paramètre. En général, vous affectez cette valeur à **eParamIO** dans les accesseurs de ligne pour rappeler à l’utilisateur que les paramètres sont ignorés.  
  
-   **DBPARAMIO\_INPUT** Paramètre d’entrée.  
  
-   **DBPARAMIO\_OUTPUT** Paramètre de sortie.  
  
-   **DBPARAMIO\_INPUT &#124; DBPARAMIO\_OUTPUT** Le paramètre est à la fois un paramètre d’entrée et de sortie.  
  
## Exemple  
 [!CODE [NVC_OLEDB_Consumer#18](../CodeSnippet/VS_Snippets_Cpp/NVC_OLEDB_Consumer#18)]  
  
## Configuration requise  
 **En\-tête :** atldbcli.h  
  
## Voir aussi  
 [Macros et fonctions globales pour les modèles du consommateur OLE DB](../../data/oledb/macros-and-global-functions-for-ole-db-consumer-templates.md)