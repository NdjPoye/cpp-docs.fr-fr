---
title: "Styles des boutons | Microsoft Docs"
ms.custom: ""
ms.date: "12/09/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "BS_DEFPUSHBUTTON"
  - "BS_NOTIFY"
  - "BS_MULTILINE"
  - "BS_AUTOCHECKBOX"
  - "BS_3STATE"
  - "BS_BITMAP"
  - "BS_TOP"
  - "BS_PUSHBUTTON"
  - "BS_PUSHLIKE"
  - "BS_AUTO3STATE"
  - "BS_CHECKBOX"
  - "BS_AUTORADIOBUTTON"
  - "BS_RADIOBUTTON"
  - "BS_OWNERDRAW"
  - "BS_LEFT"
  - "BS_USERBUTTON"
  - "BS_RIGHTBUTTON"
  - "BS_RIGHT"
  - "BS_LEFTTEXT"
  - "BS_TEXT"
  - "BS_BOTTOM"
  - "BS_GROUPBOX"
  - "BS_FLAT"
  - "BS_VCENTER"
  - "BS_ICON"
  - "BS_CENTER"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "BS_3STATE (constante)"
  - "BS_AUTO3STATE (constante)"
  - "BS_AUTOCHECKBOX (constante)"
  - "BS_AUTORADIOBUTTON (constante)"
  - "BS_BITMAP (constante)"
  - "BS_BOTTOM (constante)"
  - "BS_CENTER (constante)"
  - "BS_CHECKBOX (constante)"
  - "BS_DEFPUSHBUTTON (constante)"
  - "BS_FLAT (constante)"
  - "BS_GROUPBOX (constante)"
  - "BS_ICON (constante)"
  - "BS_LEFT (constante)"
  - "BS_LEFTTEXT (constante)"
  - "BS_MULTILINE (constante)"
  - "BS_NOTIFY (constante)"
  - "BS_OWNERDRAW (constante)"
  - "BS_PUSHBUTTON (constante)"
  - "BS_PUSHLIKE (constante)"
  - "BS_RADIOBUTTON (constante)"
  - "BS_RIGHT (constante)"
  - "BS_RIGHTBUTTON (constante)"
  - "BS_TEXT (constante)"
  - "BS_TOP (constante)"
  - "BS_USERBUTTON (constante)"
  - "BS_VCENTER (constante)"
  - "objets Button (CButton), styles des boutons"
  - "styles, objets Button"
ms.assetid: 41206f72-2b92-4250-ae32-31184046402f
caps.latest.revision: 20
caps.handback.revision: 15
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Styles des boutons
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Cette rubrique décrit les types et les styles de bouton.  
  
## Types de bouton  
 Le tableau suivant répertorie les types de bouton.  Vous pouvez choisir éventuellement l'un des éléments suivants :  Si vous ne spécifiez aucun type de bouton, le type par défaut est  `BS_PUSHBUTTON`.  
  
|Type|Description|  
|----------|-----------------|  
|`BS_3STATE`|Crée un bouton de case à cocher avec trois états : `BST_CHECKED`, `BST_INDETERMINATE` et `BST_UNCHECKED`.  Un clic sur le bouton envoie une notification `BN_CLICKED` à la fenêtre propriétaire mais ne change pas l'état du bouton.  Par défaut, le texte associé s'affiche à droite de la case à cocher.  Pour afficher un texte à gauche de la case à cocher, utilisez le style `BS_LEFTTEXT` ou `BS_RIGHTBUTTON`.|  
|`BS_AUTO3STATE`|Crée un bouton de case à cocher avec trois états : `BST_CHECKED`, `BST_INDETERMINATE` et `BST_UNCHECKED`.  Un clic sur le bouton envoie une notification `BN_CLICKED` à la fenêtre propriétaire et change l'état du bouton.  Les états du bouton défilent dans l'ordre suivant : `BST_CHECKED`, `BST_INDETERMINATE` et `BST_UNCHECKED`.  Par défaut, le texte associé s'affiche à droite de la case à cocher.  Pour afficher un texte à gauche de la case à cocher, utilisez le style `BS_LEFTTEXT` ou `BS_RIGHTBUTTON`.|  
|`BS_AUTOCHECKBOX`|Crée un bouton de case à cocher avec deux états : `BST_CHECKED` et `BST_UNCHECKED`.  Un clic sur le bouton envoie une notification `BN_CLICKED` à la fenêtre propriétaire et change l'état du bouton.  Par défaut, le texte associé s'affiche à droite de la case à cocher.  Pour afficher un texte à gauche de la case à cocher, utilisez le style `BS_LEFTTEXT` ou `BS_RIGHTBUTTON`.|  
|`BS_AUTORADIOBUTTON`|Crée une case d'option avec deux états : `BST_CHECKED` et `BST_UNCHECKED`.  Les cases d'option sont généralement utilisées dans des groupes, chaque groupe ayant au maximum une option activée à la fois.  Un clic sur le bouton envoie une notification `BN_CLICKED` à la fenêtre propriétaire, définit l'état de la case d'option sélectionnée sur `BST_CHECKED`, et définit les états de toutes les autres cases d'option du groupe de boutons sur `BST_UNCHECKED`.  Par défaut, le texte associé s'affiche à droite de la case d'option.  Pour afficher un texte à gauche du bouton d'option, utilisez le style `BS_LEFTTEXT` ou `BS_RIGHTBUTTON`.|  
|`BS_CHECKBOX`|Crée un bouton de case à cocher avec deux états : `BST_CHECKED` et `BST_UNCHECKED`.  Un clic sur le bouton envoie une notification `BN_CLICKED` à la fenêtre propriétaire mais ne change pas l'état du bouton.  Par défaut, le texte associé s'affiche à droite de la case à cocher.  Pour afficher un texte à gauche de la case à cocher, utilisez le style `BS_LEFTTEXT` ou `BS_RIGHTBUTTON`.|  
|`BS_COMMANDLINK`|Crée un bouton de liaison de commande.  Un bouton de liaison de commande est un bouton de commande propre à [!INCLUDE[windowsver](../../build/reference/includes/windowsver_md.md)] qui affiche une flèche verte à gauche du texte principal et une remarque en dessous du texte principal.  Vous pouvez définir le texte de note avec [CButton::SetNote](../Topic/CButton::SetNote.md).|  
|`BS_DEFCOMMANDLINK`|Crée un bouton de liaison de commande.  Un bouton de liaison de commande est un bouton de commande propre à [!INCLUDE[windowsver](../../build/reference/includes/windowsver_md.md)] qui affiche une flèche verte à gauche du texte principal et une remarque en dessous du texte principal.  Vous pouvez définir le texte de note avec [CButton::SetNote](../Topic/CButton::SetNote.md).  Si le bouton est dans une boîte de dialogue, l'appui de la touche ENTRÉE envoie une notification `BN_CLICKED` à la boîte de dialogue même quand le bouton n'a pas le focus d'entrée.|  
|`BS_DEFPUSHBUTTON`|Crée un bouton de commande qui a une bordure noire importante.  Si le bouton est dans une boîte de dialogue, l'appui de la touche ENTRÉE envoie une notification `BN_CLICKED` à la boîte de dialogue même quand le bouton n'a pas le focus d'entrée.|  
|`BS_DEFSPLITBUTTON`|Crée un bouton partagé.  Un bouton partagé est un bouton de commande propre à [!INCLUDE[windowsver](../../build/reference/includes/windowsver_md.md)] qui contient un bouton en regard d'une flèche de déroulement.  Lorsque vous cliquez sur le bouton, la commande par défaut est exécutée.  Lorsque vous cliquez sur la flèche déroulante, un menu de commandes supplémentaires s'affiche.  Si le bouton partagé se trouve dans une boîte de dialogue, l'appui de la touche ENTRÉE envoie une notification `BN_CLICKED` à la boîte de dialogue même si le bouton n'a pas le focus d'entrée.|  
|`BS_GROUPBOX`|Crée un rectangle dans lequel d'autres boutons peuvent être regroupés.  Le texte associé à ce style est affiché dans l'angle supérieur gauche du rectangle.|  
|`BS_OWNERDRAW`|Crée un bouton owner\-drawn.  L'infrastructure appelle la méthode `DrawItem` lorsqu'un aspect visuel du bouton a changé.  Ce style doit être défini lorsque vous utilisez la classe `CBitmapButton`.|  
|`BS_PUSHBUTTON`|Crée un bouton de commande qui envoie une notification `BN_CLICKED` à la fenêtre propriétaire lorsque l'utilisateur clique sur le bouton.|  
|`BS_RADIOBUTTON`|Crée une case d'option avec deux états : `BST_CHECKED` et `BST_UNCHECKED`.  Les cases d'option sont généralement utilisées dans des groupes, chaque groupe ayant au maximum une option activée à la fois.  Un clic sur le bouton envoie une notification `BN_CLICKED` à la fenêtre propriétaire mais ne change pas automatiquement l'état d'un bouton du groupe.  Par défaut, le texte associé s'affiche à droite de la case d'option.  Pour afficher un texte à gauche du bouton d'option, utilisez le style `BS_LEFTTEXT` ou `BS_RIGHTBUTTON`.|  
|`BS_SPLITBUTTON`|Crée un bouton partagé.  Un bouton partagé est un bouton de commande propre à [!INCLUDE[windowsver](../../build/reference/includes/windowsver_md.md)] qui contient un bouton en regard d'une flèche de déroulement.  Lorsque vous cliquez sur le bouton, la commande par défaut est exécutée.  Lorsque vous cliquez sur la flèche déroulante, un menu de commandes supplémentaires s'affiche.|  
|`BS_USERBUTTON`|Obsolète, mais fourni à des fins de compatibilité avec les versions 16 bits de Windows.  Les applications Win32 doivent utiliser à la place `BS_OWNERDRAW`.|  
  
## Styles de case d'option et de case à cocher  
 Le tableau suivant répertorie les styles spécifiques aux cases d'option et aux cases à cocher.  Ces styles sont ignorés dans tous les autres types de bouton.  Vous pouvez choisir éventuellement un ou plusieurs des éléments suivants :  
  
|Style|Description|  
|-----------|-----------------|  
|`BS_LEFTTEXT`|Lorsqu'il est combiné avec un style de case d'option ou de case à cocher, le texte apparaît à gauche de la case d'option ou de la case à cocher.|  
|`BS_RIGHTBUTTON`|Lorsqu'il est combiné avec un style de case d'option ou de case à cocher, le texte apparaît à gauche de la case d'option ou de la case à cocher.  Ce style est identique au style `BS_LEFTTEXT`.|  
|`BS_PUSHLIKE`|Permet à une case à cocher ou une case d'option d'avoir l'aspect et le comportement d'un bouton de commande.  Le bouton apparaît enfoncé lorsque son état est `BST_CHECKED`, enfoncé et estompé lorsque son état est `BST_INDETERMINATE`, puis relâché lorsque son état est `BST_UNCHECKED`.|  
  
## Styles d'alignement du texte  
 Le tableau suivant répertorie les options d'alignement horizontal et vertical du texte.  Vous pouvez choisir éventuellement l'un des éléments suivants :  
  
|Style|Description|  
|-----------|-----------------|  
|`BS_LEFT`|Aligne le texte à gauche dans le rectangle de bouton.  Toutefois, si le bouton est une case à cocher ou une case d'option qui n'a pas le style `BS_RIGHTBUTTON`, le texte est aligné à gauche du côté droit de la case à cocher ou de la case d'option.|  
|`BS_RIGHT`|Aligne le texte à droite dans le rectangle de bouton.  Toutefois, si le bouton est une case à cocher ou une case d'option qui n'a pas le style `BS_RIGHTBUTTON`, le texte est aligné à droite du côté droit de la case à cocher ou de la case d'option.|  
|`BS_CENTER`|Centre le texte horizontalement dans le rectangle de bouton.|  
|`BS_TOP`|Place le texte en haut du rectangle de bouton.|  
|`BS_BOTTOM`|Place le texte au bas du rectangle de bouton.|  
|`BS_VCENTER`|Centre le texte verticalement dans le rectangle de bouton.|  
  
## Options de contenu de bouton  
 Le tableau suivant répertorie les options qui indiquent le contenu affiché sur le bouton.  Les types de bouton qui n'affichent que du texte ignorent ces styles.  Vous pouvez choisir éventuellement l'un des éléments suivants :  
  
|Style|Description|  
|-----------|-----------------|  
|`BS_BITMAP`|Spécifie que le bouton affiche un bitmap.|  
|`BS_ICON`|Spécifie que le bouton affiche une icône.|  
|`BS_TEXT`|Spécifie que le bouton affiche du texte.|  
  
## Autres options  
 Le tableau suivant répertorie les options supplémentaires que vous pouvez utiliser avec n'importe quel type de bouton.  Vous pouvez choisir éventuellement un ou plusieurs des éléments suivants :  
  
|Style|Description|  
|-----------|-----------------|  
|`BS_FLAT`|Spécifie que le bouton est à deux dimensions et qu'il n'est pas dessiné avec l'ombrage par défaut pour créer une image en trois dimensions.|  
|`BS_MULTILINE`|Enveloppe le texte du bouton sur plusieurs lignes si la chaîne de texte est trop longue pour contenir sur une seule ligne du rectangle du bouton.|  
|`BS_NOTIFY`|Permet à un bouton d'envoyer `BN_DBLCLK`, `BN_KILLFOCUS` et des messages de notification `BN_SETFOCUS` à sa fenêtre parente.  Notez que les boutons envoient la notification `BN_CLICKED` indépendamment du fait que ce style soit spécifié ou non.|  
  
## Voir aussi  
 [Styles utilisés par MFC](../../mfc/reference/styles-used-by-mfc.md)   
 [CButton::Create](../Topic/CButton::Create.md)   
 [Styles de boutons](http://msdn.microsoft.com/library/windows/desktop/bb775951)   
 [BN\_CLICKED Notification](_win32_bn_clicked_notification)