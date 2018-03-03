---
title: "Philosophie générale de conception de classe | Documents Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- vc.classes.mfc
dev_langs:
- C++
helpviewer_keywords:
- designing classes [MFC]
- MFC, Windows API
- Visual C, Windows API calls
- classes [MFC], MFC class design
- Windows API [MFC], and MFC
ms.assetid: e6861ae0-1581-4d9c-9ddf-63f9afcdb913
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: c174b06b27e78ca61d2608b8e04205068ac436e9
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/21/2017
---
# <a name="general-class-design-philosophy"></a>Philosophie générale de conception des classes
Microsoft Windows a été conçu bien avant que le langage C++ célèbres. Étant donné que des milliers d’applications utilisent l’interface de programmation d’application (API) en langage C Windows, cette interface est conservée pour un futur prévisible. N’importe quelle interface Windows C++ doit par conséquent être créé sur l’API du langage C procédurale. Cela garantit que les applications C++ sera en mesure de coexister avec les applications C.  
  
 La bibliothèque Microsoft Foundation Class est une interface orientée objet pour Windows qui répond aux objectifs de conception suivantes :  
  
-   Réduction significative de l’effort d’écrire une application pour Windows.  
  
-   Vitesse d’exécution comparable à celle de l’API en langage C.  
  
-   Surcharge de la taille minimum de code.  
  
-   Possibilité d’appeler directement de n’importe quelle fonction C de Windows.  
  
-   Faciliter la conversion d’applications C existantes pour C++.  
  
-   Possibilité de tirer parti de la base existante de Windows en langage C expérience de programmation.  
  
-   Plus facile d’utiliser de l’API Windows avec C++ avec C.  
  
-   Plus facile à utiliser mais puissantes abstractions de compliqué des fonctionnalités telles que les contrôles ActiveX, prise en charge de la base de données, l’impression, barres d’outils et barres d’état.  
  
-   API Windows True pour C++ qui utilisent efficacement les fonctionnalités du langage C++.  
  
 Pour plus d’informations sur la conception de la bibliothèque MFC, consultez :  
  
-   [L’infrastructure d’Application](../mfc/application-framework.md)  
  
-   [Relation avec l’API du langage C](../mfc/relationship-to-the-c-language-api.md)  
  
## <a name="see-also"></a>Voir aussi  
 [Vue d’ensemble de la classe](../mfc/class-library-overview.md)

