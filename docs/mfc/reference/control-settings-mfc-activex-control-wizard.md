---
title: "Param&#232;tres du contr&#244;le, Assistant Contr&#244;le ActiveX&#160;MFC | Microsoft Docs"
ms.custom: ""
ms.date: "12/05/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "vc.appwiz.mfc.ctl.settings"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "Assistant Contrôle ActiveX MFC, paramètres du contrôle"
ms.assetid: 2ccaa4fc-0d52-413e-afa3-ecd474c3f6f0
caps.latest.revision: 16
caps.handback.revision: 12
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Param&#232;tres du contr&#244;le, Assistant Contr&#244;le ActiveX&#160;MFC
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Utilisez cette page de l'Assistant pour spécifier la façon dont vous souhaitez que le contrôle se comporte.  Par exemple, vous pouvez baser le contrôle sur les types standard de contrôle Windows, optimiser son comportement et son apparence ou indiquer que le contrôle peut jouer le rôle de conteneur pour d'autres contrôles.  
  
 Pour plus d'informations sur la façon de sélectionner des options sur cette page pour optimiser l'efficacité du contrôle, consultez [Contrôles ActiveX MFC : optimisation](../../mfc/mfc-activex-controls-optimization.md).  
  
## Liste UIElement  
 **Créer le contrôle à partir de**  
 Dans la liste, vous pouvez sélectionner le type de contrôle dont votre contrôle doit hériter.  La liste est un sous\-ensemble des classes de contrôle qui sont disponibles pour `CreateWindowEx` et les contrôles communs supplémentaires qui sont spécifiés dans commctrl.h.  Votre sélection détermine le style du contrôle dans la fonction `PreCreateWindow` du fichier *ProjName*Ctrl.cpp.  Pour plus d'informations, consultez [Contrôles ActiveX MFC : sous\-classement d'un contrôle Windows](../../mfc/mfc-activex-controls-subclassing-a-windows-control.md).  
  
|Contrôle|Description|  
|--------------|-----------------|  
|**BUTTON**|Un contrôle bouton Windows|  
|**COMBOBOX**|Un contrôle de zone de liste déroulante Windows|  
|**EDIT**|Un contrôle de champ d'édition Windows|  
|**LISTBOX**|Un contrôle de zone de liste déroulante Windows|  
|**SCROLLBAR**|Un contrôle de barre de défilement Windows|  
|**STATIQUE**|Un contrôle statique Windows|  
|**msctls\_hotkey32**|Un contrôle commun de touche d'accès rapide|  
|**msctls\_progress32**|Contrôle commun barre de progression|  
|**msctls\_statusbar32**|Contrôle commun barre d'état|  
|**msctls\_trackbar32**|Contrôle commun barre de suivi|  
|**msctls\_updown32**|Un contrôle commun de bouton toupie \(ou vers le haut\-vers le bas\)|  
|**SysAnimate32**|Un contrôle commun d'animation|  
|**SysHeader32**|Contrôle commun en\-tête|  
|**SysListView32**|Contrôle commun vue liste|  
|**SysTabControl32**|Contrôle commun tabulation|  
|**SysTreeView32**|Contrôle commun arborescence|  
  
 **Actif quand il est visible**  
 Spécifie qu'une fenêtre est créée pour le contrôle lorsqu'on y accède.  Par défaut, l'option **Actif quand il est visible** est sélectionnée.  Si vous souhaitez différer l'activation du contrôle jusqu'à ce que le conteneur le demande \(par exemple, lorsqu'un utilisateur clique sur la souris\), désactivez cette option.  Lorsque cette fonctionnalité est désactivée, le contrôle ne prend pas en charge la création de la fenêtre jusqu'à ce qu'elle soit requise.  Pour plus d'informations, consultez [Désactivation de l'option Actif quand il est visible](../../mfc/turning-off-the-activate-when-visible-option.md).  
  
 **Invisible au moment de l'exécution**  
 Spécifie que le contrôle ne possède pas d'interface utilisateur au moment de l'exécution.  Une minuterie est un type de contrôle que vous souhaiterez peut\-être pour être invisible.  
  
 **Possède une boîte de dialogue À propos de**  
 Spécifie que le contrôle comporte la boîte de dialogue Windows standard **À propos de**, dans laquelle sont affichés le numéro de version et les informations de copyright.  
  
> [!NOTE]
>  Le mode d'implémentation de l'aide que vous avez choisi et le fait d'avoir ou non intégré l'aide du contrôle à l'aide du conteneur déterminent la façon dont l'utilisateur peut accéder à l'aide du contrôle.  Pour plus d'informations sur la façon d'intégrer l'aide, sur le site Web de [la bibliothèque MSDN](http://go.microsoft.com/fwlink/?linkID=150542), recherchez « ajouter l'aide contextuelle à un contrôle ActiveX MFC ».  
  
 Lorsque vous choisissez cette option, elle insère la méthode de contrôle `AboutBox` dans la classe de contrôle du projet \(C*ProjName*Ctrl.cpp\) et ajoute AboutBox dans la table de dispatch du projet.  Cette option est activée par défaut.  
  
 **Code de dessin optimisé**  
 Spécifie que le conteneur restaure automatiquement les objets GDI d'origine après que tous les contrôles du conteneur, qui sont dessinés dans le même contexte de périphérique \(Device Context\), ont été dessinés.  Pour plus d'informations sur cette fonctionnalité, consultez [Optimisation du contrôle de dessin](../../mfc/optimizing-control-drawing.md).  
  
 **Activation sans fenêtre**  
 Spécifie que le contrôle ne génère pas de fenêtre lorsqu'il est activé.  L'activation sans fenêtre autorise les contrôles non rectangulaires ou transparents et un contrôle sans fenêtre requiert moins de charge système qu'un contrôle sans fenêtre.  Un contrôle sans fenêtre ne permet pas l'activation avec contexte de périphérique \(Device Context\) non limité ou l'activation sans scintillement.  Les conteneurs qui ont été créés avant 1996 ne prennent pas en charge l'activation sans fenêtre.  Pour plus d'informations sur la façon d'utiliser la stratégie de sécurité, consultez [Mise à disposition de l'activation sans fenêtre](../../mfc/providing-windowless-activation.md).\)  
  
 **Contexte de périphérique \(Device Context\) non découpé**  
 Substitue [COleControl::GetControlFlags](../Topic/COleControl::GetControlFlags.md) dans l'en\-tête du contrôle \(*projname*ctrl.h\) pour désactiver l'appel de `IntersectClipRect` effectué par `COleControl`.  Lorsque vous choisissez cette option, la vitesse s'améliore légèrement.  Cette fonctionnalité n'est pas disponible si l'option **Activation sans fenêtre** est activée.  Pour plus d'informations, consultez [Utilisation d'un contexte de périphérique non découpé](../../mfc/using-an-unclipped-device-context.md).  
  
 **Activation sans scintillement**  
 Élimine les opérations de dessin et le scintillement qui les accompagne normalement lors de la transition entre les états inactif et actif du contrôle.  Cette fonctionnalité n'est pas disponible si l'option **Activation sans fenêtre** est activée.  Lorsque vous choisissez cette option, l'indicateur `noFlickerActivate` figure parmi les indicateurs qui sont retournés par [COleControl::GetControlFlags](../Topic/COleControl::GetControlFlags.md).  Pour plus d'informations, consultez [Mise à disposition de l'activation sans scintillement](../../mfc/providing-flicker-free-activation.md).  
  
 **Disponible dans la boîte de dialogue Insérer un objet**  
 Spécifie que le contrôle est disponible dans la boîte de dialogue **Insérer un objet** pour les conteneurs activés.  Lorsque vous choisissez cette option, la balise `afxRegInsertable` est l'une des balises qui sont retournées par `AfxOleRegisterControlClass`.  À l'aide de la boîte de dialogue **Insérer un objet**, un utilisateur peut insérer les objets nouvellement créés ou existants dans un document composé.  
  
 **Notifications du pointeur pendant l'inactivité**  
 Permet au contrôle de toujours traiter les notifications du pointeur de souris, que ce contrôle soit actif ou non.  Lorsque vous choisissez cette option, la balise `pointerInactive` est l'une des balises qui sont retournées par [COleControl::GetControlFlags](../Topic/COleControl::GetControlFlags.md).  Pour plus d'informations sur la façon d'utiliser la stratégie de sécurité, consultez [Prise en charge de l'interaction souris pendant l'inactivité](../../mfc/providing-mouse-interaction-while-inactive.md).\)  
  
 **Se comporte comme un simple contrôle Frame**  
 Spécifie que le contrôle peut servir de conteneur à d'autres contrôles, en définissant le bit `OLEMISC_SIMPLEFRAME` du contrôle.  Pour plus d'informations, sur le site Web de [la bibliothèque MSDN](http://go.microsoft.com/fwlink/?linkID=150542) , recherchez « Simple cadre de contention de site ».  
  
 **Charge les propriétés de façon asynchrone**  
 Permet une réinitialisation des données asynchrones antérieures et déclenche un nouveau chargement de la propriété asynchrone du contrôle.  
  
## Voir aussi  
 [Contrôle ActiveX MFC \(Assistant\)](../../mfc/reference/mfc-activex-control-wizard.md)   
 [Paramètres de l’application, Assistant Contrôle ActiveX MFC](../../mfc/reference/application-settings-mfc-activex-control-wizard.md)   
 [Noms du contrôle, Assistant Contrôle ActiveX MFC](../../mfc/reference/control-names-mfc-activex-control-wizard.md)