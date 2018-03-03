---
title: "Implémentation d’une Interface (Visual C++) | Documents Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-ide
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- C++
helpviewer_keywords:
- interfaces, implementing
ms.assetid: 72f8731b-7e36-45db-8b10-7ef211a773cd
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 896ada2c46c68a794265e7344e9b7f7c7f91aebe
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/21/2017
---
# <a name="implementing-an-interface-visual-c"></a>Implémentation d'une interface (Visual C++)
Pour implémenter une interface, vous devez avoir créé un projet comme une application ATL COM ou comme une application MFC qui contient la prise en charge ATL. Vous pouvez utiliser la [Assistant Projet ATL](../atl/reference/atl-project-wizard.md) pour créer une application ATL, ou [ajouter un objet ATL à votre application MFC](../mfc/reference/adding-atl-support-to-your-mfc-project.md) pour implémenter la prise en charge ATL pour une application MFC.  
  
 Une fois que vous créez un projet, pour implémenter une interface, vous devez d’abord ajouter un objet ATL. Consultez [Ajout d’objets et des contrôles à un projet ATL](../atl/reference/adding-objects-and-controls-to-an-atl-project.md) pour obtenir la liste des Assistants permettant d’ajouter des objets à votre projet ATL.  
  
> [!NOTE]
>  L’Assistant ne prend pas en charge les boîtes de dialogue ATL, les services Web XML utilisant ATL, les objets de performance ou les compteurs de performance.  
  
 Si vous [ajouter un contrôle ATL](../atl/reference/adding-an-atl-control.md), vous pouvez spécifier s’il faut implémenter les interfaces par défaut répertoriés sur le [Interfaces](../atl/reference/interfaces-atl-control-wizard.md) page de ce Assistant et définies dans le fichier atlcom.h.  
  
 Une fois que vous avez ajouté l’objet ou le contrôle, vous pouvez implémenter autres interfaces, situées dans des bibliothèques de types disponibles, à l’aide de l’Assistant Implémentation d’Interface.  
  
 Si vous ajoutez une nouvelle interface, vous devez l’ajouter manuellement au fichier .idl du projet. Consultez [Ajout d’une nouvelle Interface dans un projet ATL](../atl/reference/adding-a-new-interface-in-an-atl-project.md) pour plus d’informations.  
  
### <a name="to-implement-an-interface"></a>Pour implémenter une interface  
  
1.  Dans Affichage de classes, cliquez sur le nom de classe pour votre objet ATL.  
  
2.  Cliquez sur **ajouter** dans le menu contextuel, puis cliquez sur **implémenter l’Interface** pour afficher les [Assistant Implémentation d’Interface](../ide/implement-interface-wizard.md).  
  
3.  Sélectionnez les interfaces à implémenter dans les bibliothèques de type approprié et cliquez sur **Terminer**.  
  
4.  Dans l’affichage de classes, développez Bases de l’objet et le nœud d’Interfaces pour afficher l’interface que vous avez implémenté, puis développez le nœud de l’interface pour afficher ses propriétés disponibles, les méthodes et les événements.  
  
    > [!NOTE]
    >  Vous pouvez également utiliser le [Explorateur d’objets](http://msdn.microsoft.com/en-us/f89acfc5-1152-413d-9f56-3dc16e3f0470) pour examiner les membres de l’interface.  
  
## <a name="see-also"></a>Voir aussi  
 [Création d’une Interface COM](../ide/creating-a-com-interface-visual-cpp.md)   
 [Modification d’une interface COM](../ide/editing-a-com-interface.md)