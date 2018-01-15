---
title: SDI et MDI | Documents Microsoft
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- frame windows [MFC], SDI applications
- frame windows [MFC], MDI applications
- MFC, windows
- single document interface (SDI) [MFC], applications
- MDI [MFC], vs. SDI
ms.assetid: bb7239d9-4759-4f63-bfff-44a04b48c067
caps.latest.revision: "9"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 7109651bc250f83d8ee7e162b647ef54dd5308d6
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/21/2017
---
# <a name="sdi-and-mdi"></a>SDI et MDI
MFC facilite le travail avec l’interface monodocument (SDI) et applications d’interface multidocument (MDI).  
  
 Les applications SDI n'autorisent qu’une seule fenêtre frame de document ouvert à la fois. Les applications MDI permettent plusieurs documents ouverts dans la même instance d’une application de fenêtres frame. Une application MDI possède une fenêtre dans le multiples MDI des fenêtres enfants, qui sont elles-mêmes des fenêtres frame, peuvent être ouverts, chacune contenant un document distinct. Dans certaines applications, les fenêtres enfants peuvent être de types différents, tels que le graphique et les fenêtres de feuille de calcul. Dans ce cas, la barre de menus permettre modifier comme fenêtres enfants MDI de types différents sont activées.  
  
> [!NOTE]
>  Sous Windows 95 et versions ultérieures, les applications sont généralement SDI, car le système d’exploitation a adopté un affichage « centré sur le document ».  
  
 Pour plus d’informations, consultez [Documents, vues et l’infrastructure](../mfc/documents-views-and-the-framework.md).  
  
## <a name="see-also"></a>Voir aussi  
 [Utilisation des classes pour l’écriture d’applications pour Windows](../mfc/using-the-classes-to-write-applications-for-windows.md)
