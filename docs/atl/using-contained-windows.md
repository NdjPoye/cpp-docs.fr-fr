---
title: Utilisation des fenêtres contenues | Documents Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.reviewer: ''
ms.suite: ''
ms.technology:
- cpp-windows
ms.tgt_pltfrm: ''
ms.topic: article
dev_langs:
- C++
helpviewer_keywords:
- ATL, windows
- windows [C++], ATL
- contained windows in ATL
ms.assetid: 7b3d79e5-b569-413f-9b98-df4f14efbe2b
caps.latest.revision: 12
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: f812b99131d63b87df8dbfd8c9afd5493d0a0140
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/21/2017
---
# <a name="using-contained-windows"></a>À l’aide de la relation contenant-contenu Windows
ATL implémente les fenêtres contenues avec [CContainedWindowT](../atl/reference/ccontainedwindowt-class.md). Une fenêtre contenue représente une fenêtre qui délègue ses messages à un objet conteneur au lieu de les gérer dans sa propre classe.  
  
> [!NOTE]
>  Vous n’avez pas besoin de dériver une classe de `CContainedWindowT` pour pouvoir utiliser les fenêtres contenues.  
  
 Avec les fenêtres contenues, vous pouvez soit surclasser une classe Windows existante ou une sous-classe une fenêtre existante. Pour créer une fenêtre qui superclasses un Windows existant de classe, commencez par spécifier le nom de classe existante dans le constructeur de la `CContainedWindowT` objet. Appelez ensuite `CContainedWindowT::Create`. Pour sous-classer une fenêtre existante, vous n’avez pas besoin de spécifier un nom de classe Windows (passez **NULL** au constructeur). Appelez simplement le `CContainedWindowT::SubclassWindow` méthode avec le handle de fenêtre sous-classée.  
  
 Vous utilisez généralement les fenêtres contenues en tant que membres de données d’une classe de conteneur. Le conteneur ne doive pas être une fenêtre ; Toutefois, il doit dériver de [CMessageMap](../atl/reference/cmessagemap-class.md).  
  
 Une fenêtre contenue peut utiliser des tables des messages de remplacement pour gérer ses messages. Si vous avez plusieurs fenêtres de relation contenant-contenu, vous devez déclarer que plusieurs autres tables des messages, chacun correspondant à une fenêtre contenue séparée.  
  
## <a name="example"></a>Exemple  
 Voici un exemple d’une classe de conteneur avec deux fenêtres contenues :  
  
 [!code-cpp[NVC_ATL_Windowing#67](../atl/codesnippet/cpp/using-contained-windows_1.h)]  
  
 Pour plus d’informations sur les fenêtres de relation contenant-contenus, consultez la [SUBEDIT](../visual-cpp-samples.md) exemple.  
  
## <a name="see-also"></a>Voir aussi  
 [Classes de fenêtre](../atl/atl-window-classes.md)

