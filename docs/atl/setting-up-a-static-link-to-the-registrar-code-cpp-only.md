---
title: "Setting Up a Static Link to the Registrar Code (C++ Only) | Microsoft Docs"
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
  - "liaison (C++), to ATL Registrar code"
  - "statically linking to ATL Registrar code"
ms.assetid: 835f5885-87a6-48fa-91e6-60988ee65538
caps.latest.revision: 11
caps.handback.revision: 6
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Setting Up a Static Link to the Registrar Code (C++ Only)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Les clients C\+\+ peuvent créer un lien statique du code du registre.  La liaison statique de l'analyseur de registre ajoute environ 5K à une version release.  
  
 La méthode la plus simple d'installer la liaison statique suppose que vous avez spécifié [DECLARE\_REGISTRY\_RESOURCEID](../Topic/DECLARE_REGISTRY_RESOURCEID.md) dans la déclaration de l'objet.  \(C'est la spécification par défaut utilisé par COM.\)  
  
### Pour créer un lien statique à l'aide de DECLARE\_REGISTRY\_RESOURCEID  
  
1.  Spécifiez [\/D](../build/reference/d-preprocessor-definitions.md)`_ATL_STATIC_REGISTRY` au lieu de \/D**\_ATL\_DLL**.  
  
2.  Recompilez.  
  
## Voir aussi  
 [Composant de registre \(Inscription\)](../atl/atl-registry-component-registrar.md)