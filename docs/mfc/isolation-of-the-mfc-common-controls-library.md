---
title: "Bibliothèque de contrôles d’isolation courantes MFC | Documents Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords: MFC, Common Controls library
ms.assetid: 7471e6f0-49b0-47f7-86e7-8d6bc3541694
caps.latest.revision: "11"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 04ed1be46d4c3d7f36bfa501bfc933fbba41e8d1
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/21/2017
---
# <a name="isolation-of-the-mfc-common-controls-library"></a>Isolement de la bibliothèque de contrôles communs MFC
La bibliothèque de contrôles communs est désormais isolée dans MFC, autorisant les différents modules (par exemple, utilisateur DLL) à utiliser les différentes versions de la bibliothèque de contrôles communs en spécifiant la version dans leur manifeste.  
  
 Une application MFC (ou le code utilisateur appelée par MFC) effectue des appels à la bibliothèque de contrôles communs API via les fonctions wrapper nommé `Afx` *FunctionName*, où *FunctionName* est le nom de commune API de contrôle. Ces fonctions wrapper sont définies dans afxcomctl32.h et afxcomctl32.inl.  
  
 Vous pouvez utiliser la [AFX_COMCTL32_IF_EXISTS](reference/run-time-object-model-services.md#afx_comctl32_if_exists) et [AFX_COMCTL32_IF_EXISTS2](reference/run-time-object-model-services.md#afx_comctl32_if_exists2) (défini dans afxcomctl32.h) pour déterminer si la bibliothèque de contrôles communs implémente une certaine API au lieu d’appeler les macros [GetProcAddress](../build/getprocaddress.md).  
  
 Techniquement, vous effectuer des appels à l’API de bibliothèque de contrôles courants via une classe wrapper, `CComCtlWrapper` (défini dans afxcomctl32.h). `CComCtlWrapper`est également chargé pour le chargement et déchargement de comctl32.dll. L’état du Module MFC contient un pointeur vers une instance de `CComCtlWrapper`. Vous pouvez accéder à la classe wrapper à l’aide du `afxComCtlWrapper` (macro).  
  
 Notez que l’appel directement les API de contrôles courants (sans utiliser les fonctions de wrapper MFC) à partir d’une MFC application ou DLL utilisateur fonctionnera dans la plupart des cas, car l’application MFC ou une DLL utilisateur est lié à la bibliothèque de contrôles communs il demandé dans son manifeste). Toutefois, le code MFC elle-même doit utiliser les wrappers, car le code MFC peut être appelée à partir de DLL utilisateur avec différentes versions de bibliothèque de contrôles communs.

