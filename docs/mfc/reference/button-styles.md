---
title: Styles des boutons | Documents Microsoft
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
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
dev_langs:
- C++
helpviewer_keywords:
- BS_NOTIFY constant
- BS_RIGHTBUTTON constant
- styles, button objects
- BS_USERBUTTON constant
- BS_VCENTER constant
- BS_PUSHLIKE constant
- BS_RADIOBUTTON constant
- BS_PUSHBUTTON constant
- BS_DEFPUSHBUTTON constant
- BS_LEFTTEXT constant
- button objects (CButton), button styles
- BS_AUTO3STATE constant
- BS_3STATE constant
- BS_OWNERDRAW constant
- BS_AUTORADIOBUTTON constant
- BS_GROUPBOX constant
- BS_BITMAP constant
- BS_CENTER constant
- BS_MULTILINE constant
- BS_BOTTOM constant
- BS_FLAT constant
- BS_AUTOCHECKBOX constant
- BS_RIGHT constant
- BS_CHECKBOX constant
- BS_LEFT constant
- BS_ICON constant
- BS_TOP constant
- BS_TEXT constant
ms.assetid: 41206f72-2b92-4250-ae32-31184046402f
caps.latest.revision: 20
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
ms.openlocfilehash: cdd577cd6915a1f3c1e05fae68f7fed47cc79236
ms.contentlocale: fr-fr
ms.lasthandoff: 02/24/2017

---
# <a name="button-styles"></a>Styles des boutons
Cette rubrique décrit les styles et les types de boutons.  
  
## <a name="button-types"></a>Types de boutons  
 Le tableau suivant répertorie les types de boutons. Vous pouvez choisir une des opérations suivantes. Si vous ne spécifiez pas un type de bouton, la valeur par défaut est `BS_PUSHBUTTON`.  
  
|Type|Description|  
|----------|-----------------|  
|`BS_3STATE`|Crée un bouton de case à cocher avec trois états : `BST_CHECKED`, `BST_INDETERMINATE`, et `BST_UNCHECKED`. Cliquez sur le bouton envoie un `BN_CLICKED` notification dans la fenêtre propriétaire mais ne modifie ne pas l’état du bouton. Par défaut, le texte associé s’affiche à droite de la case à cocher. Pour afficher le texte à gauche de la case à cocher, utilisez la `BS_LEFTTEXT` ou `BS_RIGHTBUTTON` style.|  
|`BS_AUTO3STATE`|Crée un bouton de case à cocher avec trois états : `BST_CHECKED`, `BST_INDETERMINATE`, et `BST_UNCHECKED`. Cliquez sur le bouton envoie un `BN_CLICKED` notification dans la fenêtre propriétaire et modifie l’état du bouton. Le bouton indique cycle dans l’ordre de `BST_CHECKED`, `BST_INDETERMINATE`, et `BST_UNCHECKED`. Par défaut, le texte associé s’affiche à droite de la case à cocher. Pour afficher le texte à gauche de la case à cocher, utilisez la `BS_LEFTTEXT` ou `BS_RIGHTBUTTON` style.|  
|`BS_AUTOCHECKBOX`|Crée un bouton de case à cocher avec deux états : `BST_CHECKED` et `BST_UNCHECKED`. Cliquez sur le bouton envoie un `BN_CLICKED` notification dans la fenêtre propriétaire et modifie l’état du bouton. Par défaut, le texte associé s’affiche à droite de la case à cocher. Pour afficher le texte à gauche de la case à cocher, utilisez la `BS_LEFTTEXT` ou `BS_RIGHTBUTTON` style.|  
|`BS_AUTORADIOBUTTON`|Crée un bouton radio avec deux états : `BST_CHECKED` et `BST_UNCHECKED`. Cases d’option sont généralement utilisées dans des groupes, chaque groupe ayant une option activé à la fois au maximum. En cliquant sur le bouton envoie un `BN_CLICKED` notification dans la fenêtre propriétaire, définit l’état de la case d’option sélectionnée au `BST_CHECKED`et définit les États de toutes les autres cases d’option dans un groupe à `BST_UNCHECKED`. Par défaut, le texte associé s’affiche à droite de la case d’option. Pour afficher le texte à gauche de la case d’option, utilisez la `BS_LEFTTEXT` ou `BS_RIGHTBUTTON` style.|  
|`BS_CHECKBOX`|Crée un bouton de case à cocher avec deux états : `BST_CHECKED` et `BST_UNCHECKED`. Cliquez sur le bouton envoie un `BN_CLICKED` notification dans la fenêtre propriétaire mais ne modifie ne pas l’état du bouton. Par défaut, le texte associé s’affiche à droite de la case à cocher. Pour afficher le texte à gauche de la case à cocher, utilisez la `BS_LEFTTEXT` ou `BS_RIGHTBUTTON` style.|  
|`BS_COMMANDLINK`|Crée un bouton de lien de commande. Un bouton de lien de commande est un bouton de commande spécifique à [!INCLUDE[windowsver](../../build/reference/includes/windowsver_md.md)] qui affiche une flèche verte à gauche du texte principal et une remarque sous le texte principal. Vous pouvez définir le texte de note à l’aide de [CButton::SetNote](../../mfc/reference/cbutton-class.md#setnote).|  
|`BS_DEFCOMMANDLINK`|Crée un bouton de lien de commande. Un bouton de lien de commande est un bouton de commande spécifique à [!INCLUDE[windowsver](../../build/reference/includes/windowsver_md.md)] qui affiche une flèche verte à gauche du texte principal et une remarque sous le texte principal. Vous pouvez définir le texte de note à l’aide de [CButton::SetNote](../../mfc/reference/cbutton-class.md#setnote). Si le bouton est dans une boîte de dialogue, appuyez sur la touche entrée clé envoie un `BN_CLICKED` notification à la boîte de dialogue, même si le bouton n’a pas le focus d’entrée.|  
|`BS_DEFPUSHBUTTON`|Crée un bouton de commande qui a une bordure noire épaisse. Si le bouton est dans une boîte de dialogue, appuyez sur la touche entrée clé envoie un `BN_CLICKED` notification à la boîte de dialogue, même si le bouton n’a pas le focus d’entrée.|  
|`BS_DEFSPLITBUTTON`|Crée un bouton partagé. Un bouton partagé est un bouton de commande spécifique à [!INCLUDE[windowsver](../../build/reference/includes/windowsver_md.md)] qui contient un bouton adjacent à une liste déroulante. Lorsque vous cliquez sur le bouton, la commande par défaut est exécutée. Lorsque vous cliquez sur la flèche déroulante, un menu de commandes supplémentaires s’affiche. Si le bouton de fractionnement est dans une boîte de dialogue, appuyez sur la touche entrée clé envoie un `BN_CLICKED` notification à la boîte de dialogue, même si le bouton n’a pas le focus d’entrée|  
|`BS_GROUPBOX`|Crée un rectangle dans lequel d’autres boutons peuvent être regroupés. Texte associé à ce style est affiché en haut à gauche du rectangle.|  
|`BS_OWNERDRAW`|Crée un bouton owner-drawn. Le framework appelle la `DrawItem` méthode lorsqu’un aspect visuel du bouton a changé. Ce style doit être défini lorsque vous utilisez la `CBitmapButton` classe.|  
|`BS_PUSHBUTTON`|Crée un bouton de commande qui envoie un `BN_CLICKED` notification lorsque l’utilisateur clique sur le bouton de la fenêtre propriétaire.|  
|`BS_RADIOBUTTON`|Crée un bouton radio avec deux états : `BST_CHECKED` et `BST_UNCHECKED`. Cases d’option sont généralement utilisées dans des groupes, chaque groupe ayant une option activé à la fois au maximum. Cliquez sur le bouton envoie un `BN_CLICKED` notification dans la fenêtre propriétaire mais ne change ne pas automatiquement l’état de n’importe quel bouton dans le groupe. Par défaut, le texte associé s’affiche à droite de la case d’option. Pour afficher le texte à gauche de la case d’option, utilisez la `BS_LEFTTEXT` ou `BS_RIGHTBUTTON` style.|  
|`BS_SPLITBUTTON`|Crée un bouton partagé. Un bouton partagé est un bouton de commande spécifique à [!INCLUDE[windowsver](../../build/reference/includes/windowsver_md.md)] qui contient un bouton adjacent à une liste déroulante. Lorsque vous cliquez sur le bouton, la commande par défaut est exécutée. Lorsque vous cliquez sur la flèche déroulante, un menu de commandes supplémentaires s’affiche.|  
|`BS_USERBUTTON`|Obsolète, mais fourni pour compatibilité avec les versions 16 bits de Windows. Les applications Win32 doivent utiliser `BS_OWNERDRAW` à la place.|  
  
## <a name="radio-button-and-check-box-styles"></a>Styles de case à cocher et de case d’option  
 Le tableau suivant répertorie les styles qui sont spécifiques à des cases à cocher et des cases d’option. Ces styles sont ignorés dans tous les autres types de boutons. Vous pouvez éventuellement choisir un ou plusieurs des opérations suivantes.  
  
|Style|Description|  
|-----------|-----------------|  
|`BS_LEFTTEXT`|Lorsqu’elles sont combinées avec un style de bouton ou de la case à cocher des cases d’option, le texte apparaît sur le côté gauche de la case d’option ou une case à cocher.|  
|`BS_RIGHTBUTTON`|Lorsqu’elles sont combinées avec un style de bouton ou de la case à cocher des cases d’option, le texte apparaît sur le côté gauche de la case d’option ou une case à cocher. Ce style est identique à la `BS_LEFTTEXT` style.|  
|`BS_PUSHLIKE`|Rend une case à cocher ou une case d’option Rechercher et se comporte comme un bouton de commande. Le bouton est activé lorsque son état est `BST_CHECKED`, enfoncée et grisée lorsque son état est `BST_INDETERMINATE`et publié lorsque son état est `BST_UNCHECKED`.|  
  
## <a name="text-alignment-styles"></a>Styles d’alignement de texte  
 Le tableau suivant répertorie les options d’alignement horizontal et vertical du texte. Vous pouvez choisir une des opérations suivantes.  
  
|Style|Description|  
|-----------|-----------------|  
|`BS_LEFT`|Aligne le texte dans le rectangle de bouton. Toutefois, si le bouton est une case à cocher ou de case d’option qui n’a pas la `BS_RIGHTBUTTON` style, le texte reste aligné sur le côté droit de la case à cocher ou une case d’option.|  
|`BS_RIGHT`|Droite Aligne le texte dans le rectangle de bouton. Toutefois, si le bouton est une case à cocher ou de case d’option qui n’a pas la `BS_RIGHTBUTTON` de style, le texte est aligné à droit sur le côté droit de la case à cocher ou une case d’option.|  
|`BS_CENTER`|Centre le texte horizontalement dans le rectangle de bouton.|  
|`BS_TOP`|Place le texte en haut du rectangle de bouton.|  
|`BS_BOTTOM`|Place le texte en bas du rectangle de bouton.|  
|`BS_VCENTER`|Centre le texte verticalement dans le rectangle de bouton.|  
  
## <a name="button-content-options"></a>Bouton Options de contenu  
 Le tableau suivant répertorie les options qui indiquent le texte affiché dans le bouton. Types de boutons qui affichent uniquement le texte ignorent ces styles. Vous pouvez choisir une des opérations suivantes.  
  
|Style|Description|  
|-----------|-----------------|  
|`BS_BITMAP`|Spécifie que le bouton affiche une image bitmap.|  
|`BS_ICON`|Spécifie que le bouton affiche une icône.|  
|`BS_TEXT`|Spécifie que le bouton affiche le texte.|  
  
## <a name="other-options"></a>Autres options  
 Le tableau suivant répertorie les options supplémentaires que vous pouvez utiliser n’importe quel type de bouton. Vous pouvez éventuellement choisir un ou plusieurs des opérations suivantes.  
  
|Style|Description|  
|-----------|-----------------|  
|`BS_FLAT`|Spécifie que le bouton est à deux dimensions et n’est pas dessiné avec l’ombrage par défaut pour créer une image en trois dimensions.|  
|`BS_MULTILINE`|Encapsule le texte du bouton sur plusieurs lignes si la chaîne de texte est trop longue pour tenir sur une seule ligne dans le rectangle de bouton.|  
|`BS_NOTIFY`|Active un bouton envoyer `BN_DBLCLK`, `BN_KILLFOCUS`, et `BN_SETFOCUS` des messages de notification à sa fenêtre parente. Notez que les boutons d’envoi du `BN_CLICKED` notification indépendamment de si ce style est spécifié.|  
  
## <a name="see-also"></a>Voir aussi  
 [Styles utilisés par MFC](../../mfc/reference/styles-used-by-mfc.md)   
 [CButton::Create](../../mfc/reference/cbutton-class.md#create)
 [Styles des boutons](http://msdn.microsoft.com/library/windows/desktop/bb775951)   




