---
title: "Contrôles ActiveX MFC : Accès aux propriétés ambiantes | Documents Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- MFC ActiveX controls [MFC], accessing ambient properties
- properties [MFC], accessing ambient
ms.assetid: fdc9db29-e6b0-45d2-a879-8bd60e2058a7
caps.latest.revision: "10"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: b05e6d37a0550cf157dcd43a22689c9db029b51f
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/21/2017
---
# <a name="mfc-activex-controls-accessing-ambient-properties"></a>Contrôles ActiveX MFC : accès aux propriétés ambiantes
Cet article explique comment un contrôle ActiveX peut accéder aux propriétés ambiantes de son conteneur de contrôle.  
  
 Un contrôle peut obtenir des informations sur son conteneur en accédant aux propriétés ambiantes du conteneur. Ces propriétés présentent des caractéristiques visuelles, telles que la couleur d'arrière-plan du conteneur, la police actuelle utilisée par le conteneur, et des caractéristiques opérationnelles, par exemple si le conteneur est actuellement en mode utilisateur ou en mode concepteur. Un contrôle peut utiliser les propriétés ambiantes pour adapter son apparence et son comportement au conteneur particulier dans lequel il est incorporé. Toutefois, un contrôle ne doit jamais supposer que son conteneur prend en charge une propriété ambiante particulière. En fait, certains conteneurs peuvent ne pas prendre en charge les propriétés ambiantes du tout. En l'absence d'une propriété ambiante, un contrôle doit utiliser une valeur par défaut raisonnable.  
  
 Pour accéder à une propriété ambiante, effectuez un appel à [COleControl::GetAmbientProperty](../mfc/reference/colecontrol-class.md#getambientproperty). Cette fonction attend l'ID de dispatch de la propriété ambiante en tant que premier paramètre (le fichier OLECTL.H définit les ID de dispatch pour l'ensemble standard de propriétés ambiantes).  
  
 Les paramètres de la fonction `GetAmbientProperty` sont l'ID de dispatch, une balise de variante indiquant le type de propriété attendu et un pointeur vers la mémoire dans laquelle la valeur doit être retournée. Le type de données auxquelles ce pointeur fait référence varie selon l’étiquette de variante. La fonction retourne **TRUE** le conteneur prend en charge la propriété, sinon elle retourne **FALSE**.  
  
 L'exemple de code suivant obtient la valeur de la propriété ambiante appelée "UserMode". Si la propriété n’est pas pris en charge par le conteneur, la valeur par défaut **TRUE** est supposé :  
  
 [!code-cpp[NVC_MFC_AxUI#30](../mfc/codesnippet/cpp/mfc-activex-controls-accessing-ambient-properties_1.cpp)]  
  
 Pour plus de commodité, `COleControl` fournit des fonctions d'assistance qui accèdent à plusieurs des propriétés ambiantes couramment utilisées et retourne les valeurs par défaut appropriées lorsque les propriétés ne sont pas disponibles. Ces fonctions d'assistance sont les suivantes :  
  
-   [COleControl::AmbientBackColor](../mfc/reference/colecontrol-class.md#ambientbackcolor)  
  
-   [AmbientDisplayName](../mfc/reference/colecontrol-class.md#ambientdisplayname)  
  
-   [AmbientFont](../mfc/reference/colecontrol-class.md#ambientfont)  
  
    > [!NOTE]
    >  L’appelant doit appeler **() de la version** sur la police retournée.  
  
-   [AmbientForeColor](../mfc/reference/colecontrol-class.md#ambientforecolor)  
  
-   [AmbientLocaleID](../mfc/reference/colecontrol-class.md#ambientlocaleid)  
  
-   [AmbientScaleUnits](../mfc/reference/colecontrol-class.md#ambientscaleunits)  
  
-   [AmbientTextAlign](../mfc/reference/colecontrol-class.md#ambienttextalign)  
  
-   [AmbientUserMode](../mfc/reference/colecontrol-class.md#ambientusermode)  
  
-   [AmbientUIDead](../mfc/reference/colecontrol-class.md#ambientuidead)  
  
-   [AmbientShowHatching](../mfc/reference/colecontrol-class.md#ambientshowhatching)  
  
-   [AmbientShowGrabHandles](../mfc/reference/colecontrol-class.md#ambientshowgrabhandles)  
  
 Si la valeur d’une propriété ambiante change (via une action du conteneur), la **OnAmbientPropertyChanged** fonction membre du contrôle est appelée. Remplacez cette fonction membre pour traiter cette notification. Le paramètre **OnAmbientPropertyChanged** est l’ID de dispatch de la propriété ambiante affectée. La valeur de cet ID de dispatch peut être **DISPID_UNKNOWN**, ce qui signifie qu’une ou plusieurs propriétés ambiantes a changé mais que les informations sur les propriétés ont été affectées ne sont pas disponibles.  
  
## <a name="see-also"></a>Voir aussi  
 [Contrôles ActiveX MFC](../mfc/mfc-activex-controls.md)

