---
title: "Configuration d’un lien statique avec le Code Registrar (C++ uniquement) | Documents Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- C++
helpviewer_keywords:
- statically linking to ATL Registrar code
- linking [C++], to ATL Registrar code
ms.assetid: 835f5885-87a6-48fa-91e6-60988ee65538
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: d49ed2a56738ec784c8a1a2cc3c13239f7317270
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/21/2017
---
# <a name="setting-up-a-static-link-to-the-registrar-code-c-only"></a>Configuration d’un lien statique avec le Code Registrar (C++ uniquement)
Les clients C++ peuvent créer un lien statique vers le code de Registrar. La liaison statique de l’Analyseur de Registrar ajoute les environ 5 Ko à une version Release.  
  
 La façon la plus simple pour configurer la liaison statique suppose que vous avez spécifié [DECLARE_REGISTRY_RESOURCEID](reference/registry-macros.md#declare_registry_resourceid) dans la déclaration de votre objet. (Il s’agit de la spécification de la valeur par défaut utilisée par ATL.)  
  
### <a name="to-create-a-static-link-using-declareregistryresourceid"></a>Pour créer un lien statique en utilisant DECLARE_REGISTRY_RESOURCEID  
  
1.  Spécifiez [/D](../build/reference/d-preprocessor-definitions.md) `_ATL_STATIC_REGISTRY` au lieu de /D**_ATL_DLL**.  
  
2.  Recompilez.  
  
## <a name="see-also"></a>Voir aussi  
 [Composant de Registre (inscription)](../atl/atl-registry-component-registrar.md)

