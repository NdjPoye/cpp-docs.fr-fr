---
title: "Étiquettes d’élément de contrôle d’arborescence | Documents Microsoft"
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
- tree controls [MFC], item labels
- labels, CTreeCtrl items
- CTreeCtrl class [MFC], item labels
- item labels, tree controls
- item labels
ms.assetid: fe834107-1a25-4280-aced-774c11565805
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 0d9baece3986b00aa2fbcea2b4b64217618834a8
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/21/2017
---
# <a name="tree-control-item-labels"></a>Étiquettes d’élément de contrôle d’arborescence
En règle générale, vous spécifiez le texte de l’étiquette d’un élément lors de l’ajout de l’élément au contrôle d’arborescence ([CTreeCtrl](../mfc/reference/ctreectrl-class.md)). Le `InsertItem` fonction membre peut passer un [structure TVITEM](http://msdn.microsoft.com/library/windows/desktop/bb773456) structure qui définit les propriétés de l’élément, y compris une chaîne contenant le texte de l’étiquette. `InsertItem`a plusieurs surcharges qui peuvent être appelées avec diverses combinaisons de paramètres.  
  
 Un contrôle d’arborescence alloue de la mémoire pour le stockage de chaque élément ; le texte des étiquettes occupe une partie significative de cette mémoire. Si votre application conserve une copie des chaînes dans le contrôle d’arborescence, vous pouvez réduire les besoins en mémoire du contrôle en spécifiant le **LPSTR_TEXTCALLBACK** valeur dans le **pszText** membre `TV_ITEM` ou `lpszItem` paramètre au lieu de passer les chaînes réelles au contrôle d’arborescence. À l’aide de **LPSTR_TEXTCALLBACK** provoque le contrôle d’arborescence récupérer le texte de l’étiquette d’un élément à partir de l’application chaque fois que l’élément doit être redessiné. Pour récupérer le texte, le contrôle d’arborescence envoie un [TVN_GETDISPINFO](http://msdn.microsoft.com/library/windows/desktop/bb773518) message de notification, qui inclut l’adresse d’un [structure NMTVDISPINFO](http://msdn.microsoft.com/library/windows/desktop/bb773418) structure. Vous devez répondre en définissant les membres appropriés de la structure incluse.  
  
 Un contrôle d’arborescence utilise la mémoire allouée à partir du tas du processus qui crée le contrôle d’arborescence. Le nombre maximal d’éléments dans un contrôle d’arborescence est basé sur la quantité de mémoire disponible dans le tas. Chaque élément occupe 64 octets.  
  
## <a name="see-also"></a>Voir aussi  
 [Utilisation de CTreeCtrl](../mfc/using-ctreectrl.md)   
 [Contrôles](../mfc/controls-mfc.md)

