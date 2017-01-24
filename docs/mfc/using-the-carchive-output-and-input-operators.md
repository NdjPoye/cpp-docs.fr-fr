---
title: "Utilisation des op&#233;rateurs CArchive &lt;&lt; et &gt;&gt; | Microsoft Docs"
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
  - "CArchive"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CArchive (classe), opérateurs"
  - "CArchive (classe), stocker et charger des objets"
  - "objets (C++), charger à partir de valeurs précédemment stockées"
ms.assetid: 56aef326-02dc-4992-8282-f0a4b78a064e
caps.latest.revision: 10
caps.handback.revision: 6
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Utilisation des op&#233;rateurs CArchive &lt;&lt; et &gt;&gt;
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

`CArchive` fournit les opérateurs \<\< et \>\> pour lire et écrire les types de données simples ainsi que `CObject`s vers et à partir d'un fichier.  
  
#### Pour inscrire un objet dans un fichier via une archive  
  
1.  L'exemple suivant indique comment stocker un objet dans un fichier via une archive :  
  
     [!code-cpp[NVC_MFCSerialization#7](../mfc/codesnippet/CPP/using-the-carchive-output-and-input-operators_1.cpp)]  
  
#### Pour charger un objet d'une valeur précédemment enregistrée dans un fichier  
  
1.  Le code exemple suivant montre comment charger un objet d'une valeur précédemment enregistrée dans un fichier :  
  
     [!code-cpp[NVC_MFCSerialization#8](../mfc/codesnippet/CPP/using-the-carchive-output-and-input-operators_2.cpp)]  
  
 Généralement, vous enregistrez et charger des données vers et à partir d'un fichier via une archive dans des fonctions `Serialize` de classes dérivées `CObject`\-, vous devez être déclarées avec la macro de **DECLARE\_SERIALIZE**.  Une référence à un objet `CArchive` est transmise à la fonction `Serialize`.  Vous appelez la fonction `IsLoading` de l'objet `CArchive` pour déterminer si la fonction `Serialize` a été appelée pour charger des données de fichier ou de magasin au fichier.  
  
 La fonction `Serialize` d'une classe dérivée `CObject`sérialisable \- la classe dérivée est généralement sous la forme suivante :  
  
 [!code-cpp[NVC_MFCSerialization#9](../mfc/codesnippet/CPP/using-the-carchive-output-and-input-operators_3.cpp)]  
  
 Le modèle de code ci\-dessus est exactement identique à un AppWizard création pour la fonction `Serialize` du document \(une classe dérivés de **CDocument\)**.  Ce modèle de code vous aide à écrire du code plus facile à vérifier, car le code enregistrement et le code de chargement doivent toujours être parallèles, comme dans l'exemple suivant :  
  
 [!code-cpp[NVC_MFCSerialization#10](../mfc/codesnippet/CPP/using-the-carchive-output-and-input-operators_4.cpp)]  
  
 La bibliothèque définit **\<\<** et les opérateurs de **\>\>** pour `CArchive` comme premier opérande les types et classe de données suivantes en tant que second opérande :  
  
||||  
|-|-|-|  
|`CObject*`|**SIZE et CSize**|**float**|  
|**WORD**|`CString`|**POINT** et `CPoint`|  
|`DWORD`|**BYTE**|`RECT` et `CRect`|  
|**Double**|**LONG**|`CTime` et `CTimeSpan`|  
|`Int`|**COleCurrency**|`COleVariant`|  
|`COleDateTime`|`COleDateTimeSpan`||  
  
> [!NOTE]
>  Le stockage et chargement de `CObject`s via une archive requiert une attention supplémentaire.  Pour plus d'informations, consultez [Stockage et de CObjects via une archive](../mfc/storing-and-loading-cobjects-via-an-archive.md).  
  
 Les opérateurs de **CArchive \<\<** et de **\>\>** retournent toujours une référence à l'objet `CArchive`, qui est le premier opérande.  Cela vous permet de chaîner les opérateurs, comme illustré ci\-après :  
  
 [!code-cpp[NVC_MFCSerialization#11](../mfc/codesnippet/CPP/using-the-carchive-output-and-input-operators_5.cpp)]  
  
## Voir aussi  
 [Sérialisation : sérialisation d'un objet](../mfc/serialization-serializing-an-object.md)