---
title: "Ajout d’une Page de propriétés ATL | Documents Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
dev_langs:
- C++
helpviewer_keywords:
- property pages, adding
- ATL projects, adding property pages
- controls [ATL], property pages
ms.assetid: ddf92b49-42a2-46d2-b6b8-d37baedebeca
caps.latest.revision: 12
author: mikeblome
ms.author: mblome
manager: ghogen
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
ms.translationtype: Machine Translation
ms.sourcegitcommit: d2d39abf526a58b8442107b5ee816f316ae841f5
ms.openlocfilehash: 72a8644d81857b722fd50a7e852d215bb25a2fb2
ms.contentlocale: fr-fr
ms.lasthandoff: 03/31/2017

---
# <a name="adding-an-atl-property-page"></a>Ajout d’une Page de propriétés ATL
Pour ajouter une page de propriétés bibliothèque ATL (Active Template) à votre projet, votre projet doit avoir été créé comme une application ATL ou comme une application MFC qui contient la prise en charge ATL. Vous pouvez utiliser la [Assistant Projet ATL](../../atl/reference/atl-project-wizard.md) pour créer une application ATL ou [ajouter un objet ATL à votre application MFC](../../mfc/reference/adding-atl-support-to-your-mfc-project.md) pour implémenter la prise en charge ATL pour une application MFC.  
  
 Si vous ajoutez une page de propriétés pour un contrôle, votre contrôle doit prendre en charge la [ISpecifyPropertyPagesImpl](../../atl/reference/ispecifypropertypagesimpl-class.md) interface. Par défaut, cette interface est dans la liste de dérivation de votre contrôle classe lorsque vous [créer un contrôle ATL](../../atl/reference/adding-an-atl-control.md) à l’aide de la [Assistant contrôle ATL](../../atl/reference/atl-control-wizard.md).  
  
> [!NOTE]
>  Si votre classe de contrôle n’a pas [ISpecifyPropertyPagesImpl](../../atl/reference/ispecifypropertypagesimpl-class.md) dans sa liste de dérivation, vous devez l’ajouter manuellement.  
  
### <a name="to-add-an-atl-property-page-to-your-project"></a>Pour ajouter une page de propriétés ATL à votre projet  
  
1.  Dans le **l’Explorateur de solutions** ou [affichage de classes](http://msdn.microsoft.com/en-us/8d7430a9-3e33-454c-a9e1-a85e3d2db925), cliquez sur le nom du projet auquel vous souhaitez ajouter la page de propriétés ATL.  
  
2.  Dans le menu contextuel, cliquez sur **ajouter** puis cliquez sur **ajouter une classe**.  
  
3.  Dans le [ajouter une classe](../../ide/add-class-dialog-box.md) boîte de dialogue, dans le volet Modèles, cliquez sur **Page de propriétés ATL** puis cliquez sur **ouvrir** pour afficher les [Assistant Page de propriétés ATL](../../atl/reference/atl-property-page-wizard.md).  
  
 Une fois que vous créez une page de propriétés pour un contrôle, vous devez fournir le [PROP_PAGE](property-map-macros.md#prop_page) entrée dans le mappage de propriété pour le contrôle.  
  
## <a name="see-also"></a>Voir aussi  
 [Pages de propriétés](../../atl/atl-com-property-pages.md)   
 [Notions de base des objets ATL COM](../../atl/fundamentals-of-atl-com-objects.md)   
 [Exemple : implémentation d’une page de propriétés](../../atl/example-implementing-a-property-page.md)

