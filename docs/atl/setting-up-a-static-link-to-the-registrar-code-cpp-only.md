---
title: "Configuration d’un lien statique avec le Code Registrar (C++ uniquement) | Documents Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- statically linking to ATL Registrar code
- linking [C++], to ATL Registrar code
ms.assetid: 835f5885-87a6-48fa-91e6-60988ee65538
caps.latest.revision: "11"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: b8eb77bc6f99ab6b7d8ca9d51f1a7a8549d8f0c9
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/24/2017
---
# <a name="setting-up-a-static-link-to-the-registrar-code-c-only"></a>Configuration d’un lien statique avec le Code Registrar (C++ uniquement)
Les clients C++ peuvent créer un lien statique vers le code de Registrar. La liaison statique de l’Analyseur de Registrar ajoute les environ 5 Ko à une version Release.  
  
 La façon la plus simple pour configurer la liaison statique suppose que vous avez spécifié [DECLARE_REGISTRY_RESOURCEID](reference/registry-macros.md#declare_registry_resourceid) dans la déclaration de votre objet. (Il s’agit de la spécification de la valeur par défaut utilisée par ATL.)  
  
### <a name="to-create-a-static-link-using-declareregistryresourceid"></a>Pour créer un lien statique en utilisant DECLARE_REGISTRY_RESOURCEID  
  
1.  Spécifiez [/D](../build/reference/d-preprocessor-definitions.md) `_ATL_STATIC_REGISTRY` au lieu de /D**_ATL_DLL**.  
  
2.  Recompilez.  
  
## <a name="see-also"></a>Voir aussi  
 [Composant de Registre (inscription)](../atl/atl-registry-component-registrar.md)

