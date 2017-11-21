---
title: "Définition des propriétés d’un accélérateur | Documents Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- accelerator properties
- properties [C++], accelerator properties
- Type property
- Key property
- Modifier property
ms.assetid: 0fce9156-3025-4e18-b034-e219a4c65812
caps.latest.revision: "9"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: d8a83b155b5e0a350d5c578a8dccfb9040cec3df
ms.sourcegitcommit: ca2f94dfd015e0098a6eaf5c793ec532f1c97de1
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/31/2017
---
# <a name="setting-accelerator-properties"></a>Définition des propriétés d'un accélérateur
Vous pouvez définir les propriétés d’un accélérateur dans la [fenêtre Propriétés](/visualstudio/ide/reference/properties-window) à tout moment. Vous pouvez également utiliser l'Éditeur d'accélérateurs pour modifier les propriétés d'un accélérateur dans la table d'accélérateurs. Les modifications apportées à l'aide de la fenêtre Propriétés ou de l'Éditeur d'accélérateurs ont le même résultat : elles sont immédiatement répercutées dans la table d'accélérateurs.  
  
 Il existe trois propriétés pour chaque raccourci [ID](https://www.microsoftonedoc.com/#/organizations/e6f6a65cf14f462597b64ac058dbe1d0/projects/3fedad16-eaf1-41a6-8f96-0c1949c68f32/containers/a3daf831-1c5f-4bbe-964d-503870caf874/tocpaths/3487f185-de96-4b1d-87db-034a52223160/locales/en-US):  
  
-   Le [propriété modificateur](../windows/accelerator-modifier-property.md) définit des combinaisons de touches pour l’accélérateur de contrôle.  
  
    > [!NOTE]
    >  Dans la fenêtre Propriétés, cette propriété s'affiche sous forme de trois propriétés booléennes distinctes, qui peuvent être contrôlées indépendamment : Alt, Ctrl ou Maj.  
  
-   Le [propriété de clé](../windows/accelerator-key-property.md) définit la clé réelle à utiliser comme accélérateur.  
  
-   Le [de la propriété Type](../windows/accelerator-type-property.md) détermine si la clé est interprétée comme virtuelle (VIRTKEY) ou ASCII/ANSI.  
  

  
## <a name="requirements"></a>Spécifications  
 Win32  
  
## <a name="see-also"></a>Voir aussi  
 [Touches accélérateur prédéfinies](../windows/predefined-accelerator-keys.md)   
 [Éditeurs de ressources](../windows/resource-editors.md)   
 [Éditeur d’accélérateurs](../windows/accelerator-editor.md)