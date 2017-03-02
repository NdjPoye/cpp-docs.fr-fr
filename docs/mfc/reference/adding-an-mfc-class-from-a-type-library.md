---
title: "Ajout d’une classe MFC à partir d’une bibliothèque de types | Documents Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- C++
helpviewer_keywords:
- classes [C++], adding MFC
- MFC, adding classes from type libraries
- type libraries, adding MFC classes from
ms.assetid: aba40476-3cfb-47af-990e-ae2e9e0d79cf
caps.latest.revision: 13
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
ms.sourcegitcommit: 3168772cbb7e8127523bc2fc2da5cc9b4f59beb8
ms.openlocfilehash: 0aec2c2f83dcc5857134f39f6729ce1ca9aa1acf
ms.lasthandoff: 02/24/2017

---
# <a name="adding-an-mfc-class-from-a-type-library"></a>Ajout d'une classe MFC à partir d'une bibliothèque de types
Utilisez cet Assistant pour créer une classe MFC à partir d’une interface dans une bibliothèque de types disponibles. Vous pouvez ajouter une classe MFC à une [application MFC](../../mfc/reference/creating-an-mfc-application.md), un [DLL MFC](../../mfc/reference/creating-an-mfc-dll-project.md), ou [contrôle ActiveX MFC](../../mfc/reference/creating-an-mfc-activex-control.md).  
  
> [!NOTE]
>  Il est inutile de créer un projet MFC avec Automation activé pour ajouter une classe à partir d’une bibliothèque de types.  
  
 Une bibliothèque de types contient une description binaire des interfaces exposées par un composant, en définissant les méthodes ainsi que leurs paramètres et leurs types de retour. Votre bibliothèque de types doit être inscrite pour qu’il apparaisse dans le **bibliothèques de types disponibles** liste dans Ajouter une classe à partir de l’Assistant de la bibliothèque de types. Consultez la rubrique « À l’intérieur de Distributed COM : Type Libraries and Language Integration » dans MSDN library pour plus d’informations.  
  
### <a name="to-add-an-mfc-class-from-a-type-library"></a>Pour ajouter une classe MFC à partir d’une bibliothèque de types  
  
1.  Dans le **l’Explorateur de solutions** ou [affichage de classes](http://msdn.microsoft.com/en-us/8d7430a9-3e33-454c-a9e1-a85e3d2db925), cliquez sur le nom du projet auquel vous souhaitez ajouter la classe.  
  
2.  Dans le menu contextuel, cliquez sur **ajouter**, puis cliquez sur **ajouter une classe**.  
  
3.  Dans le [ajouter une classe](../../ide/add-class-dialog-box.md) boîte de dialogue, dans le volet Modèles, cliquez sur **classe MFC à partir de la bibliothèque de types**, puis cliquez sur **Open** pour afficher les [ajouter une classe à partir de l’Assistant de la bibliothèque de types](../../mfc/reference/add-class-from-typelib-wizard.md).  
  
 Dans l’Assistant, vous pouvez ajouter plusieurs classes dans une bibliothèque de types. De même, vous pouvez ajouter des classes à partir de plus d’une bibliothèque de types dans une session d’Assistant unique.  
  
 L’Assistant crée une classe MFC, dérivée de [COleDispatchDriver](../../mfc/reference/coledispatchdriver-class.md), pour chaque interface que vous ajoutez à partir de la bibliothèque de types sélectionnée. `COleDispatchDriver`implémente le côté client d’OLE automation.  
  
## <a name="see-also"></a>Voir aussi  
 [Clients Automation](../../mfc/automation-clients.md)   
 [Clients Automation : Utilisation des bibliothèques de types](../../mfc/automation-clients-using-type-libraries.md)


