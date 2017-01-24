---
title: "Implementation of a Custom String Manager (Basic Method) | Microsoft Docs"
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
  - "IAtlStringMgr class, using"
ms.assetid: eac5d13e-cbb4-4e82-b01e-f5f2dbcb962a
caps.latest.revision: 12
caps.handback.revision: 8
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Implementation of a Custom String Manager (Basic Method)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

La façon la plus facile de personnaliser le modèle d'allocation de mémoire pour les données de chaîne est d'utiliser ATL a fourni la classe de **CAtlStringMgr** mais fournit vos propres routines d'allocation de mémoire.  Le constructeur pour **CAtlStringMgr** prend un paramètre unique : un pointeur vers un objet d' `IAtlMemMgr` .  `IAtlMemMgr` est une classe de base abstraite qui fournit une interface générique à un tas.  À l'aide de l'interface d' `IAtlMemMgr` , **CAtlStringMgr** alloue, réaffecte, et libère la mémoire utilisée pour stocker des données de chaîne.  Vous pouvez soit implémenter l'interface d' `IAtlMemMgr` vous\-même, ou utiliser l'un des cinq ATL fournissait des classes de gestionnaire de mémoire.  ATL a fourni les fonctions existants d'allocation de mémoire d'enveloppe de gestionnaires de mémoire uniquement :  
  
-   [CCRTHeap](../atl/reference/ccrtheap-class.md) Encapsule le tas CRT standard s'exécute \([malloc](../c-runtime-library/reference/malloc.md), [inscription](../c-runtime-library/reference/free.md), et [realloc](../c-runtime-library/reference/realloc.md)\)  
  
-   [CWin32Heap](../atl/reference/cwin32heap-class.md) Encapsule un handle du tas Win32, à l'aide de [HeapAlloc](http://msdn.microsoft.com/library/windows/desktop/aa366597), [HeapFree](http://msdn.microsoft.com/library/windows/desktop/aa366701), et [HeapRealloc](http://msdn.microsoft.com/library/windows/desktop/aa366704)  
  
-   [CLocalHeap](../atl/reference/clocalheap-class.md) Encapsule les API Win32 : [LocalAlloc](http://msdn.microsoft.com/library/windows/desktop/aa366723), [LocalFree](http://msdn.microsoft.com/library/windows/desktop/aa366730), et [LocalRealloc](http://msdn.microsoft.com/library/windows/desktop/aa366742)  
  
-   [CGlobalHeap](../atl/reference/cglobalheap-class.md) Encapsule les API Win32 : [GlobalAlloc](http://msdn.microsoft.com/library/windows/desktop/aa366574), [GlobalFree](http://msdn.microsoft.com/library/windows/desktop/aa366579), et [GlobalRealloc](http://msdn.microsoft.com/library/windows/desktop/aa366590).  
  
-   [CComHeap](../atl/reference/ccomheap-class.md) Encapsule les API de l'allocateur de tâche COM : [CoTaskMemAlloc](http://msdn.microsoft.com/library/windows/desktop/ms692727), [CoTaskMemFree](http://msdn.microsoft.com/library/windows/desktop/ms680722), et [CoTaskMemRealloc](http://msdn.microsoft.com/library/windows/desktop/ms687280)  
  
 Pour les besoins de la gestion de la mémoire de chaîne, la classe très utile est `CWin32Heap` car elle vous permet de créer des tas multiples d'un.  Par exemple, si vous voulez utiliser un tas séparé uniquement pour les chaînes, vous pouvez effectuer les opérations suivantes :  
  
 [!code-cpp[NVC_ATLMFC_Utilities#180](../atl-mfc-shared/codesnippet/CPP/implementation-of-a-custom-string-manager-basic-method_1.cpp)]  
  
 Pour utiliser ce gestionnaire de chaînes privé pour gérer le stockage d'une variable d' `CString` , passez un pointeur vers le gestionnaire comme paramètre au constructeur de la variable d' `CString` :  
  
 [!code-cpp[NVC_ATLMFC_Utilities#181](../atl-mfc-shared/codesnippet/CPP/implementation-of-a-custom-string-manager-basic-method_2.cpp)]  
  
## Voir aussi  
 [Memory Management with CStringT](../atl-mfc-shared/memory-management-with-cstringt.md)