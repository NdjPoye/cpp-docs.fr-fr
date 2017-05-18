---
title: "Apparence, Assistant contrôle ATL | Documents Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- vc.codewiz.class.atl.control.misc
dev_langs:
- C++
helpviewer_keywords:
- ATL Control Wizard, appearance
ms.assetid: cc16d7ff-74d7-4c15-9ebd-4b19201ff457
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
ms.translationtype: Machine Translation
ms.sourcegitcommit: 050e7483670bd32f633660ba44491c8bb3fc462d
ms.openlocfilehash: dde27a7b62f3ee3b5fe8fcacd8141e9f89ed3c98
ms.contentlocale: fr-fr
ms.lasthandoff: 02/24/2017

---
# <a name="appearance-atl-control-wizard"></a>Apparence, Assistant contrôle ATL
Insérez ici les « Résultats » résumé.  
  
 Utilisez cette page de l’Assistant pour identifier les options d’élément utilisateur supplémentaires pour le contrôle. Cette page est disponible pour les contrôles identifiés comme **les contrôles Standard** sous **type de contrôle** sur la [Options, Assistant contrôle ATL](../../atl/reference/options-atl-control-wizard.md) page.  
  
## <a name="uielement-list"></a>Liste UIElement  
 **Afficher l’état**  
 Définit l’apparence du contrôle dans le conteneur.  
  
-   **Opaque**: définit le `VIEWSTATUS_OPAQUE` bit dans le [double](http://msdn.microsoft.com/library/windows/desktop/ms687201) énumération et dessine le rectangle du contrôle tout entier passé à la [CComControlBase::OnDraw](../../atl/reference/ccomcontrolbase-class.md#ondraw) (méthode). Le contrôle apparaît complètement opaque et aucun du conteneur affiche au-delà des limites du contrôle.  
  
     Ce paramètre aide le conteneur à dessiner le contrôle plus rapidement. Si cette option n’est pas sélectionnée, le contrôle peut contenir des parties transparentes.  
  
     Seul un contrôle opaque peut avoir un arrière-plan uni.  
  
-   Définit les `VIEWSTATUS_SOLIDBKGND` bit dans le `VIEWSTATUS` (énumération). L’arrière-plan du contrôle s’affiche comme une couleur unie sans motif.  
  
     Cette option est disponible uniquement si la **Opaque** option est également sélectionnée.  
  
 **Ajouter un contrôle basé sur**  
 Définit le contrôle repose sur un type de contrôle Windows en ajoutant une [CContainedWindow](ccontainedwindowt-class.md) membre de données à la classe implémentant le contrôle. Il ajoute également une table des messages et des fonctions de gestionnaires de messages pour traiter les messages Windows pour le contrôle. Dans la liste, choisissez le type de contrôle Windows que vous souhaitez créer, le cas échéant.  

  
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
  
 **État divers**  
 Définit les options d’apparence et le comportement supplémentaires pour le contrôle.  
  
-   **Invisible au moment de l’exécution**: définit le contrôle est invisible au moment de l’exécution. Vous pouvez utiliser des contrôles invisibles pour effectuer des opérations en arrière-plan, telles que le déclenchement d’événements à intervalles réguliers.  
  
-   **Agit comme un bouton**: définit le `OLEMISC_ACTSLIKEBUTTON` bit dans le [OLEMISC](http://msdn.microsoft.com/library/windows/desktop/ms678497) énumération pour activer un contrôle d’agir comme un bouton. Si le conteneur a marqué le site du client du contrôle comme un bouton par défaut, cette option permet à votre contrôle à s’afficher comme bouton par défaut en dessinant lui-même avec une image épaisse. Consultez la page [CComControlBase::GetAmbientDisplayAsDefault](../../atl/reference/ccomcontrolbase-class.md#getambientdisplayasdefault) pour plus d’informations.  
  
-   **Agit comme étiquette**: définit le `OLEMISC_ACTSLIKELABEL` bit dans le `OLEMISC` énumération pour permettre un contrôle de remplacer l’étiquette native du conteneur. Le conteneur détermine que faire avec cet indicateur, le cas échéant.  
  
 **Autre**  
 Définit les options de comportement supplémentaires pour le contrôle.  
  
-   **Normalisation du contrôleur de domaine**: définit le contrôle pour créer un contexte de périphérique normalisé s’il est appelé à se dessiner lui-même. Cette action normalise l’apparence du contrôle, mais rend dessin moins efficace.  
  
-   **Que la fenêtre**: Spécifie que votre contrôle ne peut pas être sans fenêtre. Si vous ne sélectionnez pas cette option, votre contrôle est automatiquement sans fenêtre dans les conteneurs qui prennent en charge les objets sans fenêtre, et utilise automatiquement une fenêtre dans les conteneurs qui ne prennent pas en charge les objets sans fenêtre. Cette option force le contrôle à utiliser une fenêtre, même dans les conteneurs qui prennent en charge les objets sans fenêtre.  
  
-   **Insérer**: sélectionnez cette option pour que votre contrôle s’affichent dans le **insérer un objet** boîte de dialogue des applications telles que Word et Excel. Votre contrôle peut alors être inséré par n’importe quelle application qui prend en charge les objets incorporés dans cette boîte de dialogue.  
  
## <a name="see-also"></a>Voir aussi  
 [Assistant contrôle ATL](../../atl/reference/atl-control-wizard.md)   
 [SUBEDIT : Surclassement d’un contrôle Windows Standard](http://msdn.microsoft.com/en-us/30e46bdc-ed92-417c-b6b8-359017265a7b)


