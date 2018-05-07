---
title: Ajout d’une propriété (Visual C++) | Documents Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-ide
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- interfaces, adding properties
- properties [C++], adding to interfaces
ms.assetid: 37bd4db7-efd3-4faa-87ad-64902ed16a36
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 45eda098202fdf9286905bdc967b6aa1d7bd7035
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/04/2018
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