---
title: "Ajout d’une propriété (Visual C++) | Documents Microsoft"
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
- interfaces, adding properties
- properties [C++], adding to interfaces
ms.assetid: 37bd4db7-efd3-4faa-87ad-64902ed16a36
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 33fc8c3b5528c0ced4e0d402aec48791b7fbcb9a
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/21/2017
---
# <a name="adding-a-property-visual-c"></a>Ajout d'une propriété locale (Visual C++)
Vous pouvez utiliser la [Assistant Ajout de propriété](../ide/names-add-property-wizard.md) pour ajouter une méthode à une interface dans votre projet.  
  
### <a name="to-add-a-property-to-your-object"></a>Pour ajouter une propriété à votre objet  
  
1.  Dans [affichage de classes](http://msdn.microsoft.com/en-us/8d7430a9-3e33-454c-a9e1-a85e3d2db925), cliquez sur le nom de l’interface à laquelle vous souhaitez ajouter la propriété.  
  
    > [!NOTE]
    >  Vous pouvez également ajouter des propriétés aux dispinterfaces qui, à moins que le projet utilise des attributs, sont imbriquées dans le nœud de bibliothèque.  
  
2.  Dans le menu contextuel, cliquez sur **ajouter**, puis cliquez sur **ajouter une propriété**.  
  
3.  Dans le [Assistant Ajout de propriété](../ide/names-add-property-wizard.md), fournissez les informations pour créer la propriété.  
  
4.  Spécifiez les paramètres interface definition language (IDL) pour la propriété dans le [attributs IDL](../ide/idl-attributes-add-property-wizard.md) page de l’Assistant.  
  
5.  Cliquez sur **Terminer** pour ajouter la propriété.  
  
 Le **obtenir** et `Put` méthodes de la propriété sont affichées sous forme de deux icônes dans l’affichage de classes, sous l’interface où elle est définie. Vous pouvez double-cliquer sur l’icône pour afficher la déclaration de propriété dans le fichier .idl.  
  
-   Pour les interfaces ATL, les **obtenir** et **Put** fonctions sont ajoutées au fichier .cpp, et les références à ces fonctions sont ajoutées au fichier .h.  
  
-   Pour les dispinterfaces MFC, si vous sélectionnez **variable membre** comme type d’implémentation, une méthode et une variable sont ajoutées à la classe qui l’implémente. Si vous sélectionnez **méthodes Get/Set** comme type d’implémentation, deux méthodes sont ajoutées à la classe qui l’implémente.  
  
## <a name="see-also"></a>Voir aussi  
 [Création d’une Interface COM](../ide/creating-a-com-interface-visual-cpp.md)   
 [Modification d’une Interface COM](../ide/editing-a-com-interface.md)   
 [Le modèle d’objet composant](http://msdn.microsoft.com/library/windows/desktop/ms694363)   
 [Pointeurs d’interface et Interfaces](http://msdn.microsoft.com/library/windows/desktop/ms688484)