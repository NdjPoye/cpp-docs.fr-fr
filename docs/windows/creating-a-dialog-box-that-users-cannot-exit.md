---
title: "Création d’une boîte de dialogue que les utilisateurs ne peuvent pas quitter | Documents Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- dialog boxes, creating
- modal dialog boxes, logon screens
- logon screens
ms.assetid: 54823c27-1658-4388-bd12-0a1ce8f3899e
caps.latest.revision: "12"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 1b53c233c13ed53f4cf2ccf489da9af90ae15796
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/21/2017
---
# <a name="creating-a-dialog-box-that-users-cannot-exit"></a>Création d'une boîte de dialogue que les utilisateurs ne peuvent pas quitter
Vous pouvez créer une boîte de dialogue d’exécution qu’un utilisateur ne peut pas quitter. Ce type de boîte de dialogue est utile pour les ouvertures de session et pour le verrouillage d’application ou de document.  
  
### <a name="to-create-a-dialog-box-that-a-user-cannot-exit"></a>Pour créer une boîte de dialogue qu’un utilisateur ne peut pas quitter  
  
1.  Dans le volet **Propriétés** de la boîte de dialogue, affectez la valeur **false** à la propriété **Menu système**.  
  
     Cela désactive le menu système de boîte de dialogue et le bouton **Fermer** .  
  
2.  Dans le formulaire de boîte de dialogue, supprimez les boutons **Annuler** et **OK** .  
  
     Au moment de l’exécution, l’utilisateur ne peut pas quitter une boîte de dialogue modale qui possède ces caractéristiques.  
  
 Pour pouvoir tester ce type de boîte de dialogue, la fonction de test de boîte de dialogue détecte la touche Échap. (Échap porte également le nom de touche virtuelle VK_ESCAPE.) Quel que soit le comportement prévu de la boîte de dialogue au moment de l’exécution, vous pouvez la fermer en mode test en appuyant sur Échap.  
  
> [!NOTE]
>  Pour les applications MFC, pour créer une boîte de dialogue que les utilisateurs ne peuvent pas quitter, vous devez substituer le comportement par défaut de `OnOK` et `OnCancel` , car même si vous supprimez les boutons associés, la boîte de dialogue peut toujours être ignorée en appuyant sur Entrée ou Échap.  
  
 Pour plus d’informations sur l’ajout de ressources aux projets managés, consultez [ressources dans les applications de bureau](/dotnet/framework/resources/index).  
  
## <a name="requirements"></a>Configuration requise  
 Win32  
  
## <a name="see-also"></a>Voir aussi  
 [Comment : créer une ressource](../windows/how-to-create-a-resource.md)   
 [Fichiers de ressources](../windows/resource-files-visual-studio.md)   
 [Éditeur de boîtes de dialogue](../windows/dialog-editor.md)

