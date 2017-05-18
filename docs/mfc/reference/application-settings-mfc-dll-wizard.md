---
title: "Paramètres d’application, Assistant DLL MFC | Documents Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- vc.appwiz.mfc.dll.appset
dev_langs:
- C++
helpviewer_keywords:
- MFC DLL Wizard, application settings
ms.assetid: 0a96b94f-ae36-4975-951b-c9ffb3def21c
caps.latest.revision: 9
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
ms.sourcegitcommit: 040985df34f2613b4e4fae29498721aef15d50cb
ms.openlocfilehash: df1e3de3e1548fe4c4c340a30127d9916998ba64
ms.contentlocale: fr-fr
ms.lasthandoff: 02/24/2017

---
# <a name="application-settings-mfc-dll-wizard"></a>Paramètres de l'application, Assistant DLL MFC
Utilisez cette page de l’Assistant DLL MFC pour concevoir et ajouter des fonctionnalités de base à un nouveau projet de DLL MFC.  
  
## <a name="dll-type"></a>Type de DLL  
 Sélectionnez le type de DLL que vous souhaitez créer.  
  
 **DLL régulière à l’aide de la DLL MFC partagée**  
 Sélectionnez cette option pour lier la bibliothèque MFC à votre programme sous la forme d’une DLL partagée. À l’aide de cette option, vous ne pouvez pas partager les objets MFC entre votre DLL et l’application appelante. Votre programme effectue des appels à la bibliothèque MFC au moment de l’exécution. Cette option réduit les besoins en mémoire et espace disque de votre programme s’il est composé de plusieurs fichiers exécutables qui utilisent la bibliothèque MFC. Programmes Win32 et MFC peuvent appeler des fonctions dans votre DLL. Vous devez redistribuer les DLL MFC avec ce type de projet.  
  
 **DLL régulière avec MFC est statiquement liée**  
 Sélectionnez cette option pour lier votre programme statiquement à la bibliothèque MFC au moment de la génération. Programmes Win32 et MFC peuvent appeler des fonctions dans votre DLL. Bien que cette option augmente la taille de votre programme, il est inutile de redistribuer les DLL MFC avec ce type de projet. Vous ne pouvez pas partager les objets MFC entre votre DLL et l’application appelante.  
  
 **DLL d’extension MFC**  
 Sélectionnez cette option si vous souhaitez que votre programme pour effectuer des appels à la bibliothèque MFC au moment de l’exécution, et si vous souhaitez partager les objets MFC entre votre DLL et l’application appelante. Cette option réduit les besoins en mémoire et espace disque de votre programme, s’il est composé de plusieurs fichiers exécutables qui utilisent tous la bibliothèque MFC. Seuls les programmes MFC peuvent appeler des fonctions dans votre DLL. Vous devez redistribuer les DLL MFC avec ce type de projet.  
  
## <a name="additional-features"></a>Fonctionnalités supplémentaires  
 Permet de sélectionner si votre DLL MFC prend en charge l’automation et si elle prend en charge Windows sockets.  
  
 **Automation**  
 Sélectionnez **Automation** pour permettre à votre programme manipuler des objets implémentés dans un autre programme. En sélectionnant **Automation** expose également votre programme à d’autres clients Automation. Consultez la page [Automation](../../mfc/automation.md) pour plus d’informations.  
  
 **Sockets Windows**  
 Sélectionnez cette option pour indiquer que votre programme prend en charge Windows sockets. Les sockets Windows vous permettent d’écrire des programmes qui communiquent sur les réseaux TCP/IP.  
  
 Lorsque votre DLL MFC avec Windows sockets prise en charge est créée, [CWinApp::InitInstance](../../mfc/reference/cwinapp-class.md#initinstance) initialise la prise en charge pour les sockets et le fichier d’en-tête MFC StdAfx.h comprend AfxSock.h.  
  
## <a name="see-also"></a>Voir aussi  
 [Assistant DLL MFC](../../mfc/reference/mfc-dll-wizard.md)   
 [Création d’un projet DLL MFC](../../mfc/reference/creating-an-mfc-dll-project.md)


