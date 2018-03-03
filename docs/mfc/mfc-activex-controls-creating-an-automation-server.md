---
title: "Contrôles ActiveX MFC : Création d’un serveur Automation | Documents Microsoft"
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
- Automation servers [MFC], MFC ActiveX controls
- ActiveX controls [MFC], Automation server
- MFC ActiveX controls [MFC], Automation server
ms.assetid: e0c24ed2-d61c-49ad-a4fa-4e1098d1d39b
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 8c3de04fbbfa9f2d0b55b7e31ca02faeddfa5c12
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/21/2017
---
# <a name="mfc-activex-controls-creating-an-automation-server"></a>Contrôles ActiveX MFC : création d'un serveur Automation
Vous pouvez développer un contrôle ActiveX MFC en tant que serveur Automation pour les besoins de l’incorporation de ce contrôle dans une autre application et en appelant des méthodes dans le contrôle de l’application par programme. Un tel contrôle serait toujours disponible pour être hébergé dans un conteneur de contrôles ActiveX.  
  
### <a name="to-create-a-control-as-an-automation-server"></a>Pour créer un contrôle en tant que serveur Automation  
  
1.  [Créer](../mfc/reference/mfc-activex-control-wizard.md) le contrôle.  
  
2.  [Ajouter des méthodes](../mfc/mfc-activex-controls-methods.md).  
  
3.  Substituer [IsInvokeAllowed](../mfc/reference/colecontrol-class.md#isinvokeallowed). Pour plus d’informations, consultez l’article Q146120 de la Base de connaissances.  
  
4.  Générer le contrôle.  
  
### <a name="to-programmatically-access-the-methods-in-an-automation-server"></a>Pour accéder par programme aux méthodes dans un serveur Automation  
  
1.  Créer une application, par exemple, un [exe MFC](../mfc/reference/mfc-application-wizard.md).  
  
2.  Au début de la `InitInstance` de fonction, ajoutez la ligne suivante :  
  
     [!code-cpp[NVC_MFC_AxCont#17](../mfc/codesnippet/cpp/mfc-activex-controls-creating-an-automation-server_1.cpp)]  
  
3.  Dans l’affichage de classes, cliquez sur le nœud du projet et sélectionnez **Ajout de classes d’une typelib** pour importer la bibliothèque de types.  
  
     Cette opération ajoute des fichiers avec le .cpp et .h d’extensions de nom de fichier au projet.  
  
4.  Dans le fichier d’en-tête de la classe où vous appellerez une ou plusieurs méthodes dans le contrôle ActiveX, ajoutez la ligne suivante : `#include filename.h`, où le nom de fichier est le nom du fichier d’en-tête qui a été créé lors de l’importation de la bibliothèque de types.  
  
5.  Dans la fonction où un appel sera adressé à une méthode dans le contrôle ActiveX, ajoutez le code qui crée un objet de la classe du contrôle wrapper et créer l’objet ActiveX. Par exemple, le code MFC suivant instancie un `CCirc` (contrôle), obtient la propriété de légende et affiche le résultat lorsque l’utilisateur clique sur le bouton OK dans une boîte de dialogue :  
  
     [!code-cpp[NVC_MFC_AxCont#18](../mfc/codesnippet/cpp/mfc-activex-controls-creating-an-automation-server_2.cpp)]  
  
 Si vous ajoutez des méthodes pour le contrôle ActiveX après que l’avoir utilisé dans une application, vous pouvez commencer à l’aide de la dernière version du contrôle dans l’application en supprimant les fichiers qui ont été créés lors de l’importation de la bibliothèque de types. Puis importez de nouveau la bibliothèque de types.  
  
## <a name="see-also"></a>Voir aussi  
 [Contrôles ActiveX MFC](../mfc/mfc-activex-controls.md)

