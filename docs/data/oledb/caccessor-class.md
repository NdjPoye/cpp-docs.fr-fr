---
title: "CAccessor, classe | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "ATL.CAccessor<T>"
  - "ATL::CAccessor"
  - "CAccessor"
  - "ATL::CAccessor<T>"
  - "ATL.CAccessor"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CAccessor (classe)"
ms.assetid: b2ba959f-a686-46f3-8837-176248aef748
caps.latest.revision: 8
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 8
---
# CAccessor, classe
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Représente l'un des types d'accesseur.  
  
## Syntaxe  
  
```  
  
      template < class   
      T  
       >  
class CAccessor : public CAccessorBase, public T  
```  
  
#### Paramètres  
 `T`  
 Enregistrement utilisateur  
  
## Notes  
 Il est utilisé lorsqu'un enregistrement est statiquement lié à une source de données.  L'enregistrement contient la mémoire tampon.  Cette classe prend en charge plusieurs accesseurs sur un ensemble de lignes.  
  
 Utilisez ce type d'accesseur lorsque vous connaissez la structure et le type de la base de données.  
  
 Si votre accesseur contient les champs qui indiquent la mémoire \(par exemple `BSTR` ou une interface\) qui doit être libérée, appelez la fonction membre [CAccessorRowset::FreeRecordMemory](../../data/oledb/caccessorrowset-freerecordmemory.md) avant que l'enregistrement suivant soit lu.  
  
## Configuration requise  
 **En\-tête :** : atldbcli.h  
  
## Voir aussi  
 [Modèles du consommateur OLE DB](../../data/oledb/ole-db-consumer-templates-cpp.md)   
 [Référence des modèles du consommateur OLE DB](../../data/oledb/ole-db-consumer-templates-reference.md)