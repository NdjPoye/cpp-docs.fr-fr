---
title: "Compiler Options Macros | Microsoft Docs"
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
  - "options du compilateur, macros"
ms.assetid: a869adc6-b3de-4299-b040-9ae20b45f82c
caps.latest.revision: 17
caps.handback.revision: 6
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Compiler Options Macros
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Ces fonctionnalités spécifiques du compilateur de contrôle de macros.  
  
|||  
|-|-|  
|[\_ATL\_ALL\_WARNINGS](../Topic/_ATL_ALL_WARNINGS.md)|Un symbole qui permet aux erreurs dans les projets a converti des versions antérieures ATL.|  
|[\_ATL\_APARTMENT\_THREADED](../Topic/_ATL_APARTMENT_THREADED.md)|Définissez si un ou plusieurs de vos objets utilisent le thread cloisonné \(STA\).|  
|[\_ATL\_CSTRING\_EXPLICIT\_CONSTRUCTORS](../Topic/_ATL_CSTRING_EXPLICIT_CONSTRUCTORS.md)|Fournit les constructeurs d' `CString` explicites, empêchant les conversions involontaires.|  
|[\_ATL\_ENABLE\_PTM\_WARNING](../Topic/_ATL_ENABLE_PTM_WARNING.md)|Définissez cette macro afin d'utiliser la syntaxe conforme aux normes C\+\+, qui génère l'erreur C4867 du compilateur lorsqu'une syntaxe non standard est utilisée pour initialiser un pointeur vers une fonction membre.|  
|[\_ATL\_FREE\_THREADED](../Topic/_ATL_FREE_THREADED.md)|Définissez si un ou plusieurs de votre utilisation d'objets ou libre de threads neutre.|  
|[\_ATL\_MULTI\_THREADED](../Topic/_ATL_MULTI_THREADED.md)|Un symbole qui indique le projet comportera des objets marqués comme les deux, libre ou neutre.  Le [\_ATL\_FREE\_THREADED](../Topic/_ATL_FREE_THREADED.md) doit être utilisé à la place.|  
|[\_ATL\_NO\_AUTOMATIC\_NAMESPACE](../Topic/_ATL_NO_AUTOMATIC_NAMESPACE.md)|Un symbole qui empêché l'utilisation par défaut de l'espace de noms comme ATL.|  
|[\_ATL\_NO\_COM\_SUPPORT](../Topic/_ATL_NO_COM_SUPPORT.md)|Un symbole qui empêché le code lié au COM d'être compilé avec votre projet.|  
|[ATL\_NO\_VTABLE](../Topic/ATL_NO_VTABLE.md)|Un symbole qui empêché le pointeur vtable d'être initialisé dans le constructeur et le destructeur de la classe.|  
|[ATL\_NOINLINE](../Topic/ATL_NOINLINE.md)|Un symbole qui pointe vers une fonction ne doit pas être inline.|  
|[\_ATL\_SINGLE\_THREADED](../Topic/_ATL_SINGLE_THREADED.md)|Définissez si tous les objets utilisent le modèle monothread.|  
  
## Voir aussi  
 [Macros](../../atl/reference/atl-macros.md)