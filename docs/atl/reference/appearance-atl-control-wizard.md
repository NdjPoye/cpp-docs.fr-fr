---
title: "Apparence, Assistant contr&#244;le ATL | Microsoft Docs"
ms.custom: ""
ms.date: "12/05/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "vc.codewiz.class.atl.control.misc"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "Assistant contrôle ATL, apparence"
ms.assetid: cc16d7ff-74d7-4c15-9ebd-4b19201ff457
caps.latest.revision: 12
caps.handback.revision: 7
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Apparence, Assistant contr&#244;le ATL
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Insérez ici le résumé « Résultats de la recherche ».  
  
 Utilisez cette page de l'Assistant pour spécifier des options d'éléments utilisateur supplémentaires pour le contrôle.  Cette page est disponible pour les contrôles identifiés comme **Contrôles standard** sous **Type de contrôle**, à la page [Options, Assistant contrôle ATL](../../atl/reference/options-atl-control-wizard.md).  
  
## Liste UIElement  
 **État de la vue**  
 Définit l'apparence du contrôle à l'intérieur du conteneur.  
  
-   **Opaque** : définit le bit `VIEWSTATUS_OPAQUE` dans l'énumération [VIEWSTATUS](http://msdn.microsoft.com/library/windows/desktop/ms687201) et dessine le rectangle du contrôle tout entier passé à la méthode [CComControlBase::OnDraw](../Topic/CComControlBase::OnDraw.md).  Le contrôle apparaît complètement opaque et aucun des conteneurs ne s'affiche au\-delà des limites du contrôle.  
  
     Ce paramètre aide le conteneur à dessiner le contrôle plus rapidement.  Si cette option n'est pas sélectionnée, le contrôle peut contenir des parties transparentes.  
  
     Seul un contrôle opaque peut posséder un arrière\-plan uni.  
  
-   Définit le bit `VIEWSTATUS_SOLIDBKGND` dans l'énumération `VIEWSTATUS`.  L'arrière\-plan du contrôle s'affiche dans une couleur unie sans motif.  
  
     Cette option n'est disponible que si l'option **Opaque** est aussi sélectionnée.  
  
 **Ajouter un contrôle basé sur**  
 Définit le contrôle afin qu'il soit basé sur un type de contrôle Windows en ajoutant une donnée membre [CContainedWindow](../Topic/CContainedWindow.md) à la classe implémentant le contrôle.  Ajoute également des fonctions de gestionnaires de messages et de table des messages afin de traiter les messages Windows pour le contrôle.  Choisissez dans la liste le type de contrôle Windows que vous souhaitez créer, s'il y a lieu.  
  
-   `Button`  
  
-   `ListBox`  
  
-   `SysAnimate32`  
  
-   `SysListView32`  
  
-   `ComboBox`  
  
-   `RichEdit`  
  
-   `SysDateTimePick32`  
  
-   `SysMonthCal32`  
  
-   `ComboBoxEx32`  
  
-   `ScrollBar`  
  
-   `SysHeader32`  
  
-   `SysTabControl32`  
  
-   `Edit`  
  
-   `Static`  
  
-   `SysIPAddress32`  
  
-   `SysTreeView32`  
  
 **États divers**  
 Définit des options d'apparence et de comportement supplémentaires pour le contrôle.  
  
-   **Invisible au moment de l'exécution** : définit que le contrôle est invisible au moment de l'exécution.  Vous pouvez utiliser des contrôles invisibles pour exécuter des opérations en arrière\-plan, par exemple déclencher des événements à intervalles de temps donnés.  
  
-   **Se comporte comme un bouton** : définit le bit `OLEMISC_ACTSLIKEBUTTON` dans l'énumération [OLEMISC](http://msdn.microsoft.com/library/windows/desktop/ms678497) pour activer un contrôle afin qu'il agisse comme un bouton.  Si le conteneur a indiqué le site client du contrôle comme un bouton par défaut, sélectionner cette option permet d'afficher votre contrôle en tant que bouton par défaut entouré d'un cadre plus épais.  Consultez [CComControlBase::GetAmbientDisplayAsDefault](../Topic/CComControlBase::GetAmbientDisplayAsDefault.md) pour plus d'informations.  
  
-   **Se comporte comme une étiquette** : définit le bit `OLEMISC_ACTSLIKELABEL` dans l'énumération `OLEMISC` pour permettre à un contrôle de remplacer l'étiquette native du conteneur.  Le cas échéant, le conteneur détermine ce que vous devez faire avec cet indicateur.  
  
 **Autre**  
 Définit des options de comportement supplémentaires pour le contrôle.  
  
-   **DC normalisé** : spécifie que le contrôle doit créer un contexte de périphérique \(Device Context\) normalisé s'il est appelé à se dessiner lui\-même.  Cette action normalise l'apparence du contrôle, mais diminue l'efficacité du dessin.  
  
-   **Uniquement en fenêtre** : spécifie que votre contrôle ne peut pas être dépourvu de fenêtre.  Si vous ne sélectionnez pas cette option, votre contrôle s'affiche automatiquement sans fenêtre dans les conteneurs qui prennent en charge les objets sans fenêtre, et utilise automatiquement une fenêtre dans les conteneurs qui ne prennent pas en charge les objets sans fenêtre.  La sélection de cette option contraint votre contrôle à utiliser une fenêtre, même dans les conteneurs prenant en charge les objets sans fenêtre.  
  
-   **Insérable** : sélectionnez cette option pour que votre contrôle apparaisse dans la boîte de dialogue **Insérer un objet** d'applications telles que Word et Excel.  Votre contrôle peut ensuite être inséré par n'importe quelle application prenant en charge les objets incorporés, à l'aide de cette boîte de dialogue.  
  
## Voir aussi  
 [Assistant Contrôle ATL](../../atl/reference/atl-control-wizard.md)   
 [SUBEDIT Sample: Superclasses a Standard Windows Control](http://msdn.microsoft.com/fr-fr/30e46bdc-ed92-417c-b6b8-359017265a7b)