---
title: "Utilisation des champs de rappel dans un contr&#244;le de s&#233;lecteur de date et heure | Microsoft Docs"
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
  - "DTN_FORMATQUERY"
  - "DTN_FORMAT"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "champs de rappel dans la classe CDateTimeCtrl"
  - "CDateTimeCtrl (classe), champs de rappel"
  - "CDateTimeCtrl (classe), gérer DTN_FORMAT et DTN_FORMATQ"
  - "DateTimePicker (contrôle) (MFC)"
  - "DateTimePicker (contrôle) (MFC), champs de rappel"
  - "DTN_FORMAT (notification)"
  - "DTN_FORMATQUERY (notification)"
ms.assetid: 404f4ba9-cba7-4718-9faa-bc6b274a723f
caps.latest.revision: 11
caps.handback.revision: 7
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Utilisation des champs de rappel dans un contr&#244;le de s&#233;lecteur de date et heure
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Outre les caractères de format standard qui définissent les champs de sélecteur de date et d'heure, vous pouvez personnaliser la sortie en spécifiant certaines parties d'une chaîne de format personnalisée comme champs de rappel.  Pour déclarer un champ de rappel, incluez un ou plusieurs caractères « X » \(code ASCII 88\) n'importe où dans le corps de la chaîne de format.  Par exemple, la chaîne suivante "'Aujourd'hui, c'est : 'yy'\/'MM'\/'dd' \(jour 'X'\) '" fait que le contrôle de date et heure affiche la valeur actuelle comme année suivie du mois, de la date, et enfin le jour.  
  
> [!NOTE]
>  Le nombre de X dans un champ de rappel ne correspond pas au nombre de caractères affichés.  
  
 Vous pouvez distinguer plusieurs champs de rappel dans une chaîne personnalisée en répétant le caractère « X ».  Par conséquent, la chaîne de format « XXddddMMMdd, 'yyyXXX » contient deux champs uniques de rappel, « XX » et « XXX ».  
  
> [!NOTE]
>  Les champs de rappel sont traités en tant que champs valides, donc l'application doit être préparée à traiter les messages de notification **DTN\_WMKEYDOWN** .  
  
 Implémenter les champs de rappel du contrôle Date Time Picker se fait en trois parties :  
  
-   Initialiser la chaîne de format personnalisée  
  
-   Gérer la notification **DTN\_FORMATQUERY**  
  
-   Gérer la notification **DTN\_FORMAT**  
  
## Initialiser la chaîne de format personnalisé  
 Initialisez la chaîne personnalisée par un appel à `CDateTimeCtrl::SetFormat`.  Pour plus d'informations, consultez [Utilisation des chaînes de format personnalisé dans un contrôle de date et d'heure](../mfc/using-custom-format-strings-in-a-date-and-time-picker-control.md).  Un emplacement commun pour définir la chaîne de format personnalisé dans la fonction `OnInitDialog` de la classe de la classe de dialogue contenante ou dans la fonction `OnInitialUpdate` de la classe d'affichage contenante.  
  
## Gérer la notification DTN\_FORMATQUERY  
 Lorsque le contrôle analyse la chaîne de format et rencontre un champ de rappel, l'application envoie des messages de notification **DTN\_FORMAT** et **DTN\_FORMATQUERY**.  La chaîne de rappel du champ est incluse avec les notifications pour vous permettre de déterminer so le champ de rappel est interrogé.  
  
 La notification **DTN\_FORMATQUERY** est envoyée pour récupérer la taille maximale autorisée en pixels de la chaîne qui sera affichée dans le champ de rappel actuel.  
  
 Pour calculer correctement cette valeur, vous devez calculer la hauteur et la largeur de la chaîne, à remplacer pour le champ, en utilisant la police d'affichage du contrôle.  Le calcul réel de la chaîne est facilement effectué par un appel à la fonction Win32 [GetTextExtentPoint32](http://msdn.microsoft.com/library/windows/desktop/dd144938).  Une fois la taille déterminée, passe la valeur vers l'application et termine la fonction gestionnaire.  
  
 L'exemple suivant est une méthode pour fournir la taille de la chaîne de rappel :  
  
 [!code-cpp[NVC_MFCControlLadenDialog#8](../mfc/codesnippet/CPP/using-callback-fields-in-a-date-and-time-picker-control_1.cpp)]  
  
 Une fois la taille du champ de rappel actuel calculée, vous devez fournir une valeur pour le champ.  Cette opération s'effectue dans le gestionnaire de la notification **DTN\_FORMAT** .  
  
## Gérer la notification DTN\_FORMAT  
 La notification **DTN\_FORMAT** est utilisée par l'application pour demander la chaîne de caractères qui sera remplacée.  L'exemple de code suivant illustre une méthode possible:  
  
 [!code-cpp[NVC_MFCControlLadenDialog#9](../mfc/codesnippet/CPP/using-callback-fields-in-a-date-and-time-picker-control_2.cpp)]  
  
> [!NOTE]
>  Le pointeur vers la structure **NMDATETIMEFORMAT** se trouve en convertissant le premier paramètre du gestionnaire de notification en type approprié.  
  
## Voir aussi  
 [Utilisation de CDateTimeCtrl](../mfc/using-cdatetimectrl.md)   
 [Contrôles](../mfc/controls-mfc.md)