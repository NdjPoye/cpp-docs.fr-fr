---
title: "Détails de la prise en charge ATL ajoutée par l’Assistant ATL | Documents Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- vc.codewiz.atl.support
dev_langs:
- C++
helpviewer_keywords:
- MFC, ATL support
- ATL, MFC projects
ms.assetid: aa66bad0-008f-4886-94c1-2a0a0d04bce4
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
ms.openlocfilehash: e353df6f4f6e728fb7b866fc7690215be28b8155
ms.contentlocale: fr-fr
ms.lasthandoff: 02/24/2017

---
# <a name="details-of-atl-support-added-by-the-atl-wizard"></a>Détails de la prise en charge ATL ajoutée par l'Assistant ATL
Lorsque vous [ajouter la prise en charge ATL à un exécutable MFC ou une DLL existante](../../mfc/reference/adding-atl-support-to-your-mfc-project.md), Visual C++ apporte les modifications suivantes au projet MFC existant (dans cet exemple, le projet est appelé `MFCEXE`) :  
  
-   Deux nouveaux fichiers (un fichier .idl et un fichier .rgs, utilisés pour inscrire le serveur) sont ajoutés.  
  
-   Dans les fichiers application principale en-tête et d’implémentation (Mfcexe.h et Mfcexe.cpp), une nouvelle classe (dérivée de **CAtlMFCModule**) est ajouté. Outre la nouvelle classe, le code est ajouté à `InitInstance` pour l’inscription. Code est également ajouté à la `ExitInstance` fonction pour révoquer l’objet de classe. Dans le fichier d’en-tête, enfin, deux nouveaux fichiers d’en-tête (Initguid.h et Mfcexe_i.c) sont inclus dans le fichier d’implémentation, déclarant et initialisant les nouveaux identificateurs pour les **CAtlMFCModule**-classe dérivée.  
  
-   Pour inscrire le serveur correctement, une entrée pour le nouveau fichier .rgs est ajoutée au fichier de ressources du projet.  
  
## <a name="notes-for-dll-projects"></a>Notes de publication pour les projets DLL  
 Lorsque vous ajoutez la prise en charge ATL à un projet DLL MFC, vous verrez certaines différences. Code est ajouté à la **DLLRegisterServer** et **DLLUnregisterServer** fonctions pour l’inscription et la désinscription de la DLL. Code est également ajouté à [DllCanUnloadNow](../../atl/reference/catldllmodulet-class.md#dllcanunloadnow) et [DllGetClassObject](../../atl/reference/catldllmodulet-class.md#dllgetclassobject).  
  
## <a name="see-also"></a>Voir aussi  
 [Prise en charge ATL dans un projet MFC](../../mfc/reference/adding-atl-support-to-your-mfc-project.md)   
 [Ajout de fonctionnalités à l’aide des Assistants Code](../../ide/adding-functionality-with-code-wizards-cpp.md)   
 [Ajout d’une classe](../../ide/adding-a-class-visual-cpp.md)   
 [Ajout d’une fonction membre](../../ide/adding-a-member-function-visual-cpp.md)   
 [Ajout d’une Variable membre](../../ide/adding-a-member-variable-visual-cpp.md)   
 [Substitution d’une fonction virtuelle](../../ide/overriding-a-virtual-function-visual-cpp.md)   
 [Gestionnaire de messages MFC](../../mfc/reference/adding-an-mfc-message-handler.md)   
 [Navigation dans la Structure de classe](../../ide/navigating-the-class-structure-visual-cpp.md)

