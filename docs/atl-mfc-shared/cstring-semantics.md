---
title: "CString Semantics | Microsoft Docs"
ms.custom: ""
ms.date: "12/05/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "instructions d'assignation, assigning CString objects"
  - "CString objects, assignment semantics"
  - "semantics in Cstring"
ms.assetid: d4023480-526f-499a-85f6-324b4de5b85f
caps.latest.revision: 11
caps.handback.revision: 7
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# CString Semantics
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Bien que les objets de [CString](../atl-mfc-shared/reference/cstringt-class.md) sont des objets dynamiques qui peuvent développer, ils se comportent comme les types primitifs intégrés et les classes simples.  Chaque objet d' `CString` représente une valeur unique.  Les objets d'`CString` doivent être considérés comme chaînes réelles plutôt que comme pointeurs vers des chaînes.  
  
 Vous pouvez assigner un objet de **CString** à un autre.  Toutefois, lorsque vous modifiez un des deux objets d' `CString` , l'autre objet d' `CString` n'est pas modifié, comme illustré par l'exemple suivant :  
  
 [!code-cpp[NVC_ATLMFC_Utilities#188](../atl-mfc-shared/codesnippet/CPP/cstring-semantics_1.cpp)]  
  
 Remarque dans l'exemple que les deux objets d' `CString` sont considérés comme « égal » parce qu'ils représentent la même chaîne.  La classe d' `CString` surcharge l'opérateur d'égalité \(`==`\) pour comparer deux objets d' `CString` selon leur valeur \(contenu\) plutôt que leur identité \(adresse\).  
  
## Voir aussi  
 [Chaînes](../atl-mfc-shared/strings-atl-mfc.md)