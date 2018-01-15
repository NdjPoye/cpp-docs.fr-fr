---
title: Styles des boutons | Documents Microsoft
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- BS_DEFPUSHBUTTON
- BS_NOTIFY
- BS_MULTILINE
- BS_AUTOCHECKBOX
- BS_3STATE
- BS_BITMAP
- BS_TOP
- BS_PUSHBUTTON
- BS_PUSHLIKE
- BS_AUTO3STATE
- BS_CHECKBOX
- BS_AUTORADIOBUTTON
- BS_RADIOBUTTON
- BS_OWNERDRAW
- BS_LEFT
- BS_USERBUTTON
- BS_RIGHTBUTTON
- BS_RIGHT
- BS_LEFTTEXT
- BS_TEXT
- BS_BOTTOM
- BS_GROUPBOX
- BS_FLAT
- BS_VCENTER
- BS_ICON
- BS_CENTER
dev_langs: C++
helpviewer_keywords:
- BS_NOTIFY constant [MFC]
- BS_RIGHTBUTTON constant [MFC]
- styles [MFC], button objects
- BS_USERBUTTON constant [MFC]
- BS_VCENTER constant [MFC]
- BS_PUSHLIKE constant [MFC]
- BS_RADIOBUTTON constant [MFC]
- BS_PUSHBUTTON constant [MFC]
- BS_DEFPUSHBUTTON constant [MFC]
- BS_LEFTTEXT constant [MFC]
- button objects (CButton), button styles
- BS_AUTO3STATE constant [MFC]
- BS_3STATE constant [MFC]
- BS_OWNERDRAW constant [MFC]
- BS_AUTORADIOBUTTON constant [MFC]
- BS_GROUPBOX constant [MFC]
- BS_BITMAP constant [MFC]
- BS_CENTER constant [MFC]
- BS_MULTILINE constant [MFC]
- BS_BOTTOM constant [MFC]
- BS_FLAT constant [MFC]
- BS_AUTOCHECKBOX constant [MFC]
- BS_RIGHT constant [MFC]
- BS_CHECKBOX constant [MFC]
- BS_LEFT constant [MFC]
- BS_ICON constant [MFC]
- BS_TOP constant [MFC]
- BS_TEXT constant
ms.assetid: 41206f72-2b92-4250-ae32-31184046402f
caps.latest.revision: "20"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: b9ed2dcffbcd45215008b3d0caa802a5384367b9
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/21/2017
---
# <a name="button-styles"></a>Styles des boutons
Cette rubrique décrit les styles et les types de boutons.  
  
## <a name="button-types"></a>Types de boutons  
 Le tableau suivant répertorie les types de boutons. Vous pouvez choisir une des opérations suivantes. Si vous ne spécifiez pas un type de bouton, la valeur par défaut est `BS_PUSHBUTTON`.  
  
|Type|Description|  
|----------|-----------------|  
|`BS_3STATE`|Crée un bouton de la case à cocher avec trois états : `BST_CHECKED`, `BST_INDETERMINATE`, et `BST_UNCHECKED`. En cliquant sur le bouton envoie un `BN_CLICKED` notification dans la fenêtre propriétaire, mais ne modifie ne pas l’état du bouton. Par défaut, le texte associé s’affiche à droite de la case à cocher. Pour afficher le texte à gauche de la case à cocher, utilisez la `BS_LEFTTEXT` ou `BS_RIGHTBUTTON` style.|  
|`BS_AUTO3STATE`|Crée un bouton de la case à cocher avec trois états : `BST_CHECKED`, `BST_INDETERMINATE`, et `BST_UNCHECKED`. Cliquez sur le bouton envoie un `BN_CLICKED` notification dans la fenêtre propriétaire et modifie l’état du bouton. Le bouton indique cycle dans l’ordre de `BST_CHECKED`, `BST_INDETERMINATE`, et `BST_UNCHECKED`. Par défaut, le texte associé s’affiche à droite de la case à cocher. Pour afficher le texte à gauche de la case à cocher, utilisez la `BS_LEFTTEXT` ou `BS_RIGHTBUTTON` style.|  
|`BS_AUTOCHECKBOX`|Crée un bouton de la case à cocher avec deux états : `BST_CHECKED` et `BST_UNCHECKED`. Cliquez sur le bouton envoie un `BN_CLICKED` notification dans la fenêtre propriétaire et modifie l’état du bouton. Par défaut, le texte associé s’affiche à droite de la case à cocher. Pour afficher le texte à gauche de la case à cocher, utilisez la `BS_LEFTTEXT` ou `BS_RIGHTBUTTON` style.|  
|`BS_AUTORADIOBUTTON`|Crée un bouton radio avec deux états : `BST_CHECKED` et `BST_UNCHECKED`. Cases d’option sont généralement utilisées dans des groupes, chaque groupe ayant une option activé à la fois au maximum. En cliquant sur le bouton envoie un `BN_CLICKED` notification à la fenêtre propriétaire, définit l’état de la case d’option où vous avez cliqué à `BST_CHECKED`et définit les États de toutes les autres cases d’option dans le groupe de boutons pour `BST_UNCHECKED`. Par défaut, le texte associé s’affiche à droite de la case d’option. Pour afficher le texte à gauche de la case d’option, utilisez le `BS_LEFTTEXT` ou `BS_RIGHTBUTTON` style.|  
|`BS_CHECKBOX`|Crée un bouton de la case à cocher avec deux états : `BST_CHECKED` et `BST_UNCHECKED`. En cliquant sur le bouton envoie un `BN_CLICKED` notification dans la fenêtre propriétaire, mais ne modifie ne pas l’état du bouton. Par défaut, le texte associé s’affiche à droite de la case à cocher. Pour afficher le texte à gauche de la case à cocher, utilisez la `BS_LEFTTEXT` ou `BS_RIGHTBUTTON` style.|  
|`BS_COMMANDLINK`|Crée un bouton de lien de commande. Un bouton de lien de commande est un bouton de commande spécifique à [!INCLUDE[windowsver](../../build/reference/includes/windowsver_md.md)] qui affiche une flèche verte vers la gauche du texte principal et une note sous le texte principal. Vous pouvez définir le texte de note à l’aide de [CButton::SetNote](../../mfc/reference/cbutton-class.md#setnote).|  
|`BS_DEFCOMMANDLINK`|Crée un bouton de lien de commande. Un bouton de lien de commande est un bouton de commande spécifique à [!INCLUDE[windowsver](../../build/reference/includes/windowsver_md.md)] qui affiche une flèche verte vers la gauche du texte principal et une note sous le texte principal. Vous pouvez définir le texte de note à l’aide de [CButton::SetNote](../../mfc/reference/cbutton-class.md#setnote). Si le bouton se trouve dans une boîte de dialogue, en appuyant sur l’entrée de clé envoie un `BN_CLICKED` notification à la boîte de dialogue, même lorsque le bouton n’a pas le focus d’entrée.|  
|`BS_DEFPUSHBUTTON`|Crée un bouton de commande qui a une bordure noire lourde. Si le bouton se trouve dans une boîte de dialogue, en appuyant sur l’entrée de clé envoie un `BN_CLICKED` notification à la boîte de dialogue, même lorsque le bouton n’a pas le focus d’entrée.|  
|`BS_DEFSPLITBUTTON`|Crée un bouton partagé. Un bouton partagé est un bouton de commande spécifique à [!INCLUDE[windowsver](../../build/reference/includes/windowsver_md.md)] qui contient un bouton adjacent à une flèche de déroulement. Lorsque vous cliquez sur le bouton, la commande par défaut est exécutée. Lorsque vous cliquez sur la flèche déroulante, un menu de commandes supplémentaires s’affiche. Si le bouton partagé est dans une boîte de dialogue, en appuyant sur l’entrée de clé envoie un `BN_CLICKED` notification à la boîte de dialogue, même lorsque le bouton n’a pas le focus d’entrée|  
|`BS_GROUPBOX`|Crée un rectangle dans lequel les autres boutons peuvent être regroupés. Texte associé à ce style est affiché en haut à gauche du rectangle.|  
|`BS_OWNERDRAW`|Crée un bouton owner-drawn. Le framework appelle la `DrawItem` méthode lorsqu’un aspect visuel du bouton a changé. Ce style doit être défini lorsque vous utilisez la `CBitmapButton` classe.|  
|`BS_PUSHBUTTON`|Crée un bouton de commande qui envoie un `BN_CLICKED` notification dans la fenêtre propriétaire lorsque l’utilisateur clique sur le bouton.|  
|`BS_RADIOBUTTON`|Crée un bouton radio avec deux états : `BST_CHECKED` et `BST_UNCHECKED`. Cases d’option sont généralement utilisées dans des groupes, chaque groupe ayant une option activé à la fois au maximum. En cliquant sur le bouton envoie un `BN_CLICKED` notification dans la fenêtre propriétaire, mais ne change ne pas automatiquement l’état d’un bouton dans le groupe. Par défaut, le texte associé s’affiche à droite de la case d’option. Pour afficher le texte à gauche de la case d’option, utilisez le `BS_LEFTTEXT` ou `BS_RIGHTBUTTON` style.|  
|`BS_SPLITBUTTON`|Crée un bouton partagé. Un bouton partagé est un bouton de commande spécifique à [!INCLUDE[windowsver](../../build/reference/includes/windowsver_md.md)] qui contient un bouton adjacent à une flèche de déroulement. Lorsque vous cliquez sur le bouton, la commande par défaut est exécutée. Lorsque vous cliquez sur la flèche déroulante, un menu de commandes supplémentaires s’affiche.|  
|`BS_USERBUTTON`|Obsolète, mais fourni pour la compatibilité avec les versions 16 bits de Windows. Les applications Win32 doivent utiliser `BS_OWNERDRAW` à la place.|  
  
## <a name="radio-button-and-check-box-styles"></a>Case d’option et les Styles de case à cocher  
 Le tableau suivant répertorie les styles qui sont spécifiques à des cases à cocher et des cases d’option. Ces styles sont ignorés dans tous les autres types de boutons. Vous pouvez éventuellement choisir une ou plusieurs des opérations suivantes.  
  
|Style|Description|  
|-----------|-----------------|  
|`BS_LEFTTEXT`|Lorsqu’elles sont combinées avec un style de bouton ou de la case à cocher des cases d’option, le texte apparaît sur le côté gauche de la case d’option ou une case à cocher.|  
|`BS_RIGHTBUTTON`|Lorsqu’elles sont combinées avec un style de bouton ou de la case à cocher des cases d’option, le texte apparaît sur le côté gauche de la case d’option ou une case à cocher. Ce style est identique à la `BS_LEFTTEXT` style.|  
|`BS_PUSHLIKE`|Rend une case à cocher ou une case d’option ressemblent et se comportent comme un bouton de commande. Le bouton est activé lorsque son état est `BST_CHECKED`, enfoncée et estompé lorsque son état est `BST_INDETERMINATE`et libérée lorsque son état est `BST_UNCHECKED`.|  
  
## <a name="text-alignment-styles"></a>Styles d’alignement de texte  
 Le tableau suivant répertorie les options d’alignement horizontal et vertical du texte. Vous pouvez choisir une des opérations suivantes.  
  
|Style|Description|  
|-----------|-----------------|  
|`BS_LEFT`|Aligne le texte dans le rectangle de bouton à gauche. Toutefois, si le bouton est une case à cocher ou de case d’option qui n’a pas la `BS_RIGHTBUTTON` reste de style, le texte aligné sur le côté droit de la case à cocher ou une case d’option.|  
|`BS_RIGHT`|Aligne le texte dans le rectangle de bouton à droite. Toutefois, si le bouton est une case à cocher ou de case d’option qui n’a pas la `BS_RIGHTBUTTON` de style, le texte est aligné à droit sur le côté droit de la case à cocher ou une case d’option.|  
|`BS_CENTER`|Centre le texte horizontalement dans le rectangle de bouton.|  
|`BS_TOP`|Place le texte en haut du rectangle de bouton.|  
|`BS_BOTTOM`|Place le texte en bas du rectangle de bouton.|  
|`BS_VCENTER`|Centre le texte verticalement dans le rectangle de bouton.|  
  
## <a name="button-content-options"></a>Options de contenu de bouton  
 Le tableau suivant répertorie les options qui indiquent ce qui est affiché dans le bouton. Types de boutons qui affichent uniquement du texte ignorent ces styles. Vous pouvez choisir une des opérations suivantes.  
  
|Style|Description|  
|-----------|-----------------|  
|`BS_BITMAP`|Spécifie que le bouton affiche une image bitmap.|  
|`BS_ICON`|Spécifie que le bouton affiche une icône.|  
|`BS_TEXT`|Spécifie que le bouton affiche le texte.|  
  
## <a name="other-options"></a>Autres options  
 Le tableau suivant répertorie les options supplémentaires que vous pouvez utiliser avec n’importe quel type de bouton. Vous pouvez éventuellement choisir une ou plusieurs des opérations suivantes.  
  
|Style|Description|  
|-----------|-----------------|  
|`BS_FLAT`|Spécifie que le bouton est à deux dimensions et n’est pas dessiné avec un ombrage par défaut pour créer une image en trois dimensions.|  
|`BS_MULTILINE`|Encapsule le texte du bouton sur plusieurs lignes si la chaîne de texte est trop longue pour tenir sur une seule ligne dans le rectangle de bouton.|  
|`BS_NOTIFY`|Active un bouton envoyer `BN_DBLCLK`, `BN_KILLFOCUS`, et `BN_SETFOCUS` des messages de notification à sa fenêtre parente. Notez que les boutons d’envoi du `BN_CLICKED` notification indépendamment de si ce style est spécifié.|  
  
## <a name="see-also"></a>Voir aussi  
 [Styles utilisés par MFC](../../mfc/reference/styles-used-by-mfc.md)   
 [CButton::Create](../../mfc/reference/cbutton-class.md#create) [Styles des boutons](http://msdn.microsoft.com/library/windows/desktop/bb775951)   



