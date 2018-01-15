---
title: "Affectation des touches d’accès rapide aux commandes de Menu | Documents Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- access keys [C++], checking
- menus, shortcut keys
- keyboard shortcuts [C++], command assignments
- access keys [C++], assigning
- mnemonics, adding to menus
- keyboard shortcuts [C++], uniqueness checking
- mnemonics, uniqueness checking
- Check Mnemonics command
ms.assetid: fbcf1a00-af6a-4171-805a-0ac01d4e8b0d
caps.latest.revision: "9"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: ccf64739d0a54b5a96551b3a8145dc3c3f8378c6
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/21/2017
---
# <a name="assigning-access-keys-to-menu-commands"></a>Assignation de touches d'accès rapide à des commandes de menu
Vous pouvez affecter une touche d’accès rapide (un mnémonique qui permet à l’utilisateur de sélectionner le menu à l’aide du clavier) à vos menus et commandes de menu.  
  
### <a name="to-assign-an-access-shortcut-key-to-a-menu-command"></a>Pour affecter une touche d’accès (raccourci) à une commande de menu  
  
1.  Tapez un « et commercial » (**&**) devant une lettre dans le nom de menu ou le nom de commande pour spécifier cette lettre comme touche d’accès rapide correspondante. Par exemple « &Fichier » définit Alt+F comme touche de raccourci pour le menu Fichier dans les applications écrites pour Microsoft Windows.  
  
     L’élément de menu fournit un indice visuel signalant qu’une touche de raccourci est affectée à l’une de lettres. La lettre qui suit que le symbole & apparaît soulignée (en fonction du système d’exploitation).  
  
    > [!NOTE]
    >  Assurez-vous que toutes les touches d’accès rapide d’un menu sont uniques en cliquant avec le bouton droit sur le menu et en choisissant **Vérifier les mnémoniques** dans le menu contextuel.  
  
 Pour plus d’informations sur l’ajout de ressources aux projets managés, consultez [ressources dans les applications de bureau](/dotnet/framework/resources/index) dans le *Guide du développeur .NET Framework.* Pour plus d’informations sur l’ajout manuel des fichiers de ressources aux projets managés, l’accès aux ressources, affichage de ressources statiques et l’assignation de chaînes de ressources aux propriétés, consultez [création de fichiers de ressources pour les applications de bureau](/dotnet/framework/resources/creating-resource-files-for-desktop-apps). Pour plus d’informations sur la globalisation et localisation des ressources dans les applications managées, consultez [globalisation et localisation d’Applications .NET Framework](/dotnet/standard/globalization-localization/index).  
  
 Configuration requise  
  
 Win32  
  
## <a name="see-also"></a>Voir aussi  
 [Éditeur de menus](../windows/menu-editor.md)