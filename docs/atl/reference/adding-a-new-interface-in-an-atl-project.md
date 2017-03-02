---
title: "Ajout d’une nouvelle Interface à un projet ATL | Documents Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- vc.appwiz.ATL.interface
dev_langs:
- C++
helpviewer_keywords:
- interfaces, adding to ATL objects
- Implement Interface ATL wizard
- controls [ATL], interfaces
- ATL projects, adding interfaces
ms.assetid: 7d34b023-2c6b-4155-aca3-d47a40968063
caps.latest.revision: 10
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
translationtype: Machine Translation
ms.sourcegitcommit: 5187996fc377bca8633360082d07f7ec8a68ee57
ms.openlocfilehash: 8e4916c60310dd8dcbf0bb9e8c1f151309a32621
ms.lasthandoff: 02/24/2017

---
# <a name="adding-a-new-interface-in-an-atl-project"></a>Ajout d’une nouvelle Interface à un projet ATL
Lorsque vous ajoutez une interface à votre objet ou contrôle, vous créez des fonctions d’extraite pour chaque méthode dans cette interface. Dans votre objet ou le contrôle, vous pouvez ajouter uniquement les interfaces que qui se trouvent actuellement dans une bibliothèque de types existante. En outre, la classe dans laquelle vous ajoutez l’interface doit implémenter la [BEGIN_COM_MAP](http://msdn.microsoft.com/library/ead2a1e3-334d-44ad-bb1f-b94bb14c2333) (macro) ou, si le projet utilise des attributs, il doit avoir le `coclass` attribut.  
  
 Vous pouvez ajouter une nouvelle interface à votre contrôle de deux façons : manuellement ou à l’aide des Assistants code dans l’affichage de classes.  
  
### <a name="to-use-code-wizards-in-class-view-to-add-an-interface-to-an-existing-object-or-control"></a>Pour utiliser les Assistants code dans l’affichage de classes pour ajouter une interface à un objet existant ou d’un contrôle  
  
1.  Dans [affichage de classes](http://msdn.microsoft.com/en-us/8d7430a9-3e33-454c-a9e1-a85e3d2db925), cliquez sur le nom de classe d’un contrôle. Par exemple, un contrôle total ou contrôle composite ou toute autre classe de contrôle qui implémente une macro BEGIN_COM_MAP dans son fichier d’en-tête.  
  
2.  Dans le menu contextuel, cliquez sur **ajouter**, puis cliquez sur **implémenter l’Interface**.  
  
3.  Sélectionnez les interfaces à implémenter dans le [Assistant Implémentation d’Interface](../../ide/implement-interface-wizard.md). Si l’interface n’existe pas dans aucune des typelibs disponibles, puis vous devez ajouter manuellement au fichier .idl.  
  
### <a name="to-add-a-new-interface-manually"></a>Pour ajouter une nouvelle interface manuellement  
  
1.  Ajoutez la définition de la nouvelle interface dans le fichier .idl.  
  
2.  Dérivez votre objet ou le contrôle de l’interface.  
  
3.  Créer un nouveau [COM_INTERFACE_ENTRY](http://msdn.microsoft.com/library/c5363b8b-a1a2-471e-ad3a-d472f6c356c5) pour l’interface ou, si le projet utilise des attributs, ajoutez le `coclass` attribut.  
  
4.  Implémentez les méthodes sur l’interface.  
  
## <a name="see-also"></a>Voir aussi  
 [Assistant Projet ATL](../../atl/reference/atl-project-wizard.md)   
 [Types de projets Visual C++](../../ide/visual-cpp-project-types.md)   
 [Création de projets de bureau à l’aide des Assistants Application](../../ide/creating-desktop-projects-by-using-application-wizards.md)   
 [Programmation avec ATL et le Code C Run-Time](../../atl/programming-with-atl-and-c-run-time-code.md)   
 [Principes de base des objets ATL COM](../../atl/fundamentals-of-atl-com-objects.md)   
 [Configurations des projets ATL par défaut](../../atl/reference/default-atl-project-configurations.md)


