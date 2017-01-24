---
title: "Fonctionnalit&#233;s de l&#39;interface utilisateur, Assistant Application MFC | Microsoft Docs"
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
  - "vc.appwiz.mfc.exe.ui"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "Assistant Application MFC, fonctionnalités de l’interface utilisateur"
ms.assetid: 59e7b829-a665-42eb-be23-3f2a36eb2dad
caps.latest.revision: 12
caps.handback.revision: 8
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Fonctionnalit&#233;s de l&#39;interface utilisateur, Assistant Application MFC
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Cette rubrique explique les options que vous pouvez utiliser pour spécifier l'apparence de votre application.  Les fonctionnalités d'interface utilisateur disponibles pour votre projet dépendent du type d'application spécifié dans la page [Type d'application, Assistant Application MFC](../../mfc/reference/application-type-mfc-application-wizard.md) de l'Assistant Application MFC.  Par exemple, si vous créez une application dotée d'une interface monodocument, vous ne pouvez pas ajouter les styles du frame enfant.  
  
 **Styles du frame principal**  
 Définit les fonctionnalités du frame de fenêtre principal de l'application.  
  
|Option|Description|  
|------------|-----------------|  
|**Frame épais**|Crée une fenêtre possédant une bordure de redimensionnement.  Valeur par défaut.|  
|**Bouton Réduire**|Inclut un bouton de réduction dans la fenêtre frame principale.  Valeur par défaut.|  
|**Bouton Agrandir**|Inclut un bouton d'agrandissement dans la fenêtre frame principale.  Valeur par défaut.|  
|**Réduite**|Ouvre une fenêtre frame principale sous la forme d'une icône.|  
|**Agrandie**|Ouvre la fenêtre frame principale en plein écran.|  
|**Menu Système**|Inclut un menu Système dans la fenêtre frame principale.  Valeur par défaut.|  
|**Boîte de dialogue À propos de**|Inclut une case **À propos de** pour l'application.  L'utilisateur peut accéder à cette boîte de dialogue à partir du menu **Aide** de l'application.  Il s'agit de la valeur par défaut et il est impossible de la changer, à moins de sélectionner **Basée sur des boîtes de dialogue** dans la page [Type d'application, Assistant Application MFC](../../mfc/reference/application-type-mfc-application-wizard.md).<br /><br /> **Remarque** Une option qui n'est pas disponible indique habituellement que l'Assistant n'applique pas l'option au projet, que la case à cocher correspondant à l'élément non disponible soit activée ou désactivée.  Dans le cas présent, l'Assistant ajoute toujours une boîte de dialogue **À propos de** au projet, sauf si vous spécifiez d'abord que le projet est basé sur une boîte de dialogue, puis que vous désactivez la case à cocher.|  
|**Barre d'état initiale**|Ajoute une barre d'état à votre application.  La barre d'état contient des indicateurs automatiques pour les touches VERR. MAJ, VERR. NUM et DÉFIL du clavier, ainsi qu'une ligne de message qui affiche les chaînes d'aide pour les commandes de menu et les boutons de barre d'outils.  Le fait de cliquer sur cette option entraîne également l'ajout de commandes de menu permettant d'afficher ou de masquer la barre d'état.  Par défaut, une application possède une barre d'état.  Cette option n'est pas disponible pour les types d'applications basées sur des boîtes de dialogue.|  
|**Fenêtre fractionnée**|Fournit une barre de fractionnement.  La barre de fractionnement sépare les vues principales de l'application.  Dans une application dotée d'une interface multidocument \(MDI\), la fenêtre cliente du frame enfant MDI est une fenêtre fractionnée ; dans une application dotée d'une interface monodocument \(SDI\) et dans une application prenant en charge plusieurs documents de niveau supérieur, la fenêtre cliente du frame principal est une fenêtre fractionnée.  Cette option n'est pas disponible pour les types d'applications basées sur des boîtes de dialogue.|  
  
 **Styles du frame enfant**  
 Spécifie l'apparence et l'état initial des frames enfants dans votre application.  Les styles du frame enfant sont uniquement disponibles pour les applications dotées d'une interface MDI.  
  
|Option|Description|  
|------------|-----------------|  
|**Bouton Réduire enfant**|Spécifie si une fenêtre enfant possède un bouton réduire \(activé par défaut\).|  
|**Bouton Agrandir enfant**|Spécifie si une fenêtre enfant possède un bouton agrandir \(activé par défaut\).|  
|**Enfant agrandi**|Spécifie si une fenêtre enfant est initialement agrandie en définissant l'indicateur cs.style **WS\_MAXIMIZE** dans la fonction membre [PreCreateWindow](../Topic/CWnd::PreCreateWindow.md) de `CChildFrame`.|  
  
 **Barres de commandes \(menu\/barre d'outils\/ruban\)**  
 Indique si votre application inclut des menus, barres d'outils et\/ou un ruban.  Cette option n'est pas disponible pour les applications basées sur des boîtes de dialogue.  
  
|Option|Description|  
|------------|-----------------|  
|**Utiliser un menu classique**|Spécifie que votre application contient un menu classique qui ne peut être déplacé.|  
|**Utiliser une barre d'outils d'ancrage classique**|Ajoute une barre d'outils Windows standard à votre application.  La barre d'outils contient des boutons permettant d'effectuer les opérations suivantes : créer un document, ouvrir et enregistrer des fichiers de document, couper, copier, coller ou imprimer du texte et passer en mode d'aide.  Le fait d'activer cette option entraîne également l'ajout de commandes de menu permettant d'afficher ou de masquer la barre d'outils.|  
|**Utiliser une barre d'outils de navigateur**|Ajoute une barre d'outils de style Internet Explorer à votre application.|  
|**Utiliser une barre de menus et une barre d'outils**|Indique que votre application contient une barre de menus et une barre d'outils qui peuvent être déplacées.|  
|**Barres d'outils et images définies par l'utilisateur**|Permet à l'utilisateur de personnaliser la barre d'outils et les images de barre d'outils pendant l'exécution.|  
|**Comportement de menu personnalisé**|Spécifie si le menu contient la liste complète d'éléments à l'ouverture ou s'il contient uniquement les commandes que l'utilisateur utilise le plus fréquemment.|  
|**Utiliser un ruban**|Utilise un ruban de type Office 2007 dans votre application au lieu d'une barre de menus ou d'une barre d'outils.|  
  
 **Titre de la boîte de dialogue**  
 Destiné uniquement aux applications basées sur [CDialog Class](../../mfc/reference/cdialog-class.md). Ce titre apparaît dans la barre de titre de la boîte de dialogue.  Pour modifier ce champ, vous devez d'abord sélectionner l'option **Basée sur des boîtes de dialogue** sous **Type d'application**.  Pour plus d'informations, consultez [Type d'application, Assistant Application MFC](../../mfc/reference/application-type-mfc-application-wizard.md).  
  
## Voir aussi  
 [Assistant Application MFC](../../mfc/reference/mfc-application-wizard.md)