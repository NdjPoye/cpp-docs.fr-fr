---
title: "Fonctionnalités d’Interface utilisateur, Assistant Application MFC | Documents Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- vc.appwiz.mfc.exe.ui
dev_langs:
- C++
helpviewer_keywords:
- MFC Application Wizard, user interface features
ms.assetid: 59e7b829-a665-42eb-be23-3f2a36eb2dad
caps.latest.revision: 12
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
ms.sourcegitcommit: 040985df34f2613b4e4fae29498721aef15d50cb
ms.openlocfilehash: 80513d5f6b8dff5b8108a5b80f1d8db1e53d0ea0
ms.lasthandoff: 02/24/2017

---
# <a name="user-interface-features-mfc-application-wizard"></a>Fonctionnalités de l’interface utilisateur, Assistant Application MFC
Cette rubrique explique les options que vous pouvez utiliser pour spécifier l’apparence de votre application. Les fonctionnalités d’interface utilisateur disponibles pour votre projet dépendent du type d’application que vous avez spécifié dans le [Type d’Application, Assistant Application MFC](../../mfc/reference/application-type-mfc-application-wizard.md) page de l’Assistant Application MFC. Par exemple, si vous créez une application d’interface monodocument, vous ne pouvez pas ajouter de styles du frame enfant.  
  
 **Styles du frame principal**  
 Définit les fonctionnalités du frame de fenêtre principale de votre application.  
  
|Option|Description|  
|------------|-----------------|  
|**Frame épais**|Crée une fenêtre comportant une bordure de redimensionnement. Valeur par défaut.|  
|**Bouton réduire**|Inclut un réduire dans la fenêtre frame principale. Valeur par défaut.|  
|**Bouton d’agrandissement**|Inclut un agrandissement dans la fenêtre frame principale. Valeur par défaut.|  
|**Réduit**|Ouvre la fenêtre frame principale sous forme d’icône.|  
|**Agrandie**|Ouvre la fenêtre frame principale à la taille totale de l’affichage.|  
|**Menu système**|Inclut un menu système dans la fenêtre frame principale. Valeur par défaut.|  
|**À propos de la zone**|Inclut un **sur** pour l’application. L’utilisateur peut accéder à cette zone à partir de l’application **aide** menu. La valeur par défaut et non modifiable, sauf si vous sélectionnez **basée sur un dialogue**, dans le [Type d’Application, Assistant Application MFC](../../mfc/reference/application-type-mfc-application-wizard.md) page.<br /><br /> **Remarque** en règle générale, une option non disponible indique que l’Assistant ne s’applique pas l’option au projet, si la case à cocher de l’élément non disponible est activée ou désactivée. Dans ce cas, l’Assistant ajoute toujours une **sur** boîte au projet, sauf si vous spécifiez d’abord le projet en tant que boîte de dialogue en fonction et puis décochez la case.|  
|**Barre d’état initiale**|Ajoute une barre d’état à votre application. La barre d’état contient des indicateurs automatiques pour les touches VERR. MAJ, VERR. NUM et défil du clavier et d’une ligne de message qui affiche l’aide de chaînes pour les commandes de menu et barre d’outils de boutons. Cette option ajoute également des commandes de menu pour afficher ou masquer la barre d’état. Par défaut, une application possède une barre d’état. Non disponible pour les types d’application basée sur une boîte de dialogue.|  
|**Fenêtre fractionnée**|Fournit une barre de fractionnement. La barre de fractionnement fractionne les vues principales de l’application. Dans une application d’interface (multidocument MDI) document plusieurs, fenêtre du client du frame enfant MDI est une fenêtre fractionnée, et dans une application SDI (interface) de document unique et plusieurs applications de document de niveau supérieur, fenêtre du client du frame principal est une fenêtre fractionnée. Non disponible pour les types d’application basée sur une boîte de dialogue.|  
  
 **Styles du frame enfant**  
 Spécifie l’apparence et l’état initial des frames enfants dans votre application. Styles du frame enfant sont disponibles pour les applications MDI uniquement.  
  
|Option|Description|  
|------------|-----------------|  
|**Bouton réduire enfant**|Spécifie si une fenêtre enfant possède un bouton réduire (activé par défaut).|  
|**Bouton Agrandir enfant**|Spécifie si une fenêtre enfant possède un bouton Agrandir (activé par défaut).|  
|**Enfant agrandi**|Spécifie si une fenêtre enfant est initialement agrandie en définissant l’indicateur cs.style **WS_MAXIMIZE** dans les [PreCreateWindow](../../mfc/reference/cwnd-class.md#precreatewindow) fonction membre de `CChildFrame`.|  
  
 **Barres de commandes (menu, barre d’outils/ruban)**  
 Indique si votre application inclut des menus, barres d’outils et/ou un ruban. Non disponible pour les applications basées sur la boîte de dialogue.  
  
|Option|Description|  
|------------|-----------------|  
|**Utiliser un menu classique**|Spécifie que votre application contienne un menu classique, non déplaçable.|  
|**Utilisez une barre d’outils d’ancrage classique**|Ajoute une barre d’outils Windows standard à votre application. La barre d’outils contient des boutons pour la création d’un document ; ouvrir et enregistrer des fichiers de document ; Couper, copier, coller ou imprimer du texte ; et en entrant en mode d’aide. L’activation de cette option ajoute également des commandes de menu pour afficher ou masquer la barre d’outils.|  
|**Utilisez une barre d’outils de style navigateur**|Ajoute une barre d’outils de style Internet Explorer à votre application.|  
|**Utilisez une barre de menus et la barre d’outils**|Indique que votre application contienne une barre de menus déplaçable et une barre d’outils.|  
|**Images et définies par l’utilisateur de barres d’outils**|Permet à l’utilisateur de personnaliser la barre d’outils et les images de barre d’outils lors de l’exécution.|  
|**Comportement de menu personnalisé**|Spécifie si le menu contient la liste complète des éléments de l’ouverture ou s’il contient uniquement les commandes que l’utilisateur utilise le plus fréquemment.|  
|**Utiliser un ruban**|Utilise un ruban de type Office 2007 dans votre application au lieu d’une barre de menus ou la barre d’outils.|  
  
 **Titre de la boîte de dialogue**  
 Pour [CDialog (classe)](../../mfc/reference/cdialog-class.md)-uniquement, les applications basées sur ce titre s’affiche dans la barre de titre de la boîte de dialogue. Pour modifier ce champ, vous devez d’abord sélectionner le **basée sur un dialogue** option sous **type d’Application**. Pour plus d’informations, consultez [Type d’Application, Assistant Application MFC](../../mfc/reference/application-type-mfc-application-wizard.md).  
  
## <a name="see-also"></a>Voir aussi  
 [Assistant Application MFC](../../mfc/reference/mfc-application-wizard.md)


