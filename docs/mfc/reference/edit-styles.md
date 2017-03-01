---
title: Modifier les Styles | Documents Microsoft
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- ES_READONLY
- ES_WANTRETURN
- ES_UPPERCASE
- ES_NUMBER
- ES_AUTOHSCROLL
- ES_LOWERCASE
- ES_RIGHT
- ES_MULTILINE
- ES_PASSWORD
- ES_NOHIDESEL
- ES_OEMCONVERT
- ES_LEFT
- ES_CENTER
dev_langs:
- C++
helpviewer_keywords:
- ES_WANTRETURN constant
- edit styles [MFC]
- ES_RIGHT constant
- ES_READONLY constant
- ES_PASSWORD constant
- ES_MULTILINE constant
- ES_LEFT constant
- ES_AUTOVSCROLL constant
- ES_OEMCONVERT constant
- ES_LOWERCASE constant
- ES_NUMBER constant
- ES_UPPERCASE constant
- ES_NOHIDESEL constant
- ES_AUTOHSCROLL constant
- ES_CENTER constant
ms.assetid: e6291dd6-f2cb-4ce2-ac31-32272526625c
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
ms.openlocfilehash: 275e0d2dede038bdbe9061bc8051408442aa70bf
ms.lasthandoff: 02/24/2017

---
# <a name="edit-styles"></a>Modifier les styles
-   **ES_AUTOHSCROLL** défile automatiquement le texte à droite de 10 caractères lorsque l’utilisateur tape un caractère à la fin de la ligne. Lorsque l’utilisateur appuie sur la touche entrée, le contrôle défile tout le texte à la position 0.  
  
-   **ES_AUTOVSCROLL** fait défiler automatiquement le texte d’une page lorsque l’utilisateur appuie sur entrée sur la dernière ligne.  
  
-   **ES_CENTER** Centre le texte dans une seule ligne ou un multiline contrôle d’édition.  
  
-   **ES_LEFT** gauche-aligne le texte dans une seule ligne ou un multiligne contrôle d’édition.  
  
-   **ES_LOWERCASE** convertit tous les caractères en minuscules lorsqu’ils sont tapés dans le contrôle d’édition.  
  
-   **ES_MULTILINE** désigne un contrôle d’édition de plusieurs lignes. (La valeur par défaut est la seule ligne.) Si le **ES_AUTOVSCROLL** style est spécifié, le contrôle edit affiche autant de lignes que possible et fait défiler verticalement lorsque l’utilisateur appuie sur la touche ENTRÉE. Si **ES_AUTOVSCROLL** est ne pas accordée, le contrôle edit affiche autant de lignes que possible et les signaux sonores si la touche entrée quand plus aucune ligne ne peut être affichés. Si le **ES_AUTOHSCROLL** style est spécifié, le contrôle d’édition de plusieurs lignes défile horizontalement lorsque le signe insertion dépasse le bord droit du contrôle. Pour démarrer une nouvelle ligne, l’utilisateur doit appuyer sur ENTRÉE. Si **ES_AUTOHSCROLL** est ne pas accordée, le contrôle renvoie les mots au début de la ligne suivante lorsque cela est nécessaire, une nouvelle ligne est également démarrée si vous appuyez sur ENTRÉE. La position de la propriété wordwrap est déterminée par la taille de la fenêtre. Si la taille de la fenêtre change, les changements de position wordwrap et le texte s’affiche de nouveau. Les contrôles d’édition de plusieurs lignes peuvent avoir des barres de défilement. Un contrôle d’édition avec barres de défilement traite ses propres messages de la barre de défilement. Modifier des contrôles sans défilement de barres de défilement comme décrit ci-dessus et traiter les messages de défilement envoyés par la fenêtre parente.  
  
-   **ES_NOHIDESEL** normalement, un contrôle d’édition masque la sélection lorsque le contrôle perd le focus d’entrée et inverse la sélection lorsque le contrôle reçoit le focus d’entrée. Spécification de **ES_NOHIDESEL** supprime cette action par défaut.  
  
-   **ES_NUMBER** permet uniquement de chiffres doit être entrée dans le contrôle d’édition.  
  
-   **ES_OEMCONVERT** texte entré dans le contrôle d’édition est converti dans le jeu de caractères ANSI pour le jeu de caractères OEM et puis de nouveau en ANSI. Cela garantit une conversion correcte des caractères lorsque l’application appelle la `AnsiToOem` fonction pour convertir une chaîne ANSI dans le contrôle d’édition en caractères OEM de Windows. Ce style est particulièrement utile pour les contrôles d’édition qui contiennent des noms de fichiers.  
  
-   **ES_PASSWORD** affiche tous les caractères sous la forme d’un astérisque (**\***) lorsqu’ils sont tapés dans le contrôle d’édition. Une application peut utiliser le `SetPasswordChar` fonction membre pour modifier le caractère qui s’affiche.  
  
-   **ES_READONLY** empêche l’utilisateur d’entrer ou de modifier du texte dans le contrôle d’édition.  
  
-   **ES_RIGHT** contrôle d’édition de droite-Aligne le texte dans une seule ligne ou un multiligne.  
  
-   **ES_UPPERCASE** convertit tous les caractères en majuscules lorsqu’ils sont tapés dans le contrôle d’édition.  
  
-   **ES_WANTRETURN** Spécifie qu’un retour chariot est insérée lorsque l’utilisateur appuie sur la touche entrée lors de la saisie de texte dans un contrôle d’édition de plusieurs lignes dans une boîte de dialogue. Sans ce style, en appuyant sur la touche entrée a le même effet que d’appuyer sur le bouton de commande par défaut de zones boîte de dialogue. Ce style n’a aucun effet sur une seule ligne contrôle d’édition.  
  
## <a name="see-also"></a>Voir aussi  
 [Styles utilisés par MFC](../../mfc/reference/styles-used-by-mfc.md)   
 [CEdit::Create](../../mfc/reference/cedit-class.md#create)   
 [Modifier les Styles de contrôle](http://msdn.microsoft.com/library/windows/desktop/bb775464)


