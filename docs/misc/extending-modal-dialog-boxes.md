---
title: "Cr&#233;ation de bo&#238;tes de dialogue modales | Microsoft Docs"
ms.custom: ""
ms.date: "11/17/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-csharp"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "boîtes de dialogue modales dans les extensions Visual Studio"
  - "extensions Visual Studio, boîtes de dialogue modales"
ms.assetid: 478743dc-9fd9-46d7-9739-859fb8841a4f
caps.latest.revision: 11
caps.handback.revision: 11
manager: "douge"
---
# Cr&#233;ation de bo&#238;tes de dialogue modales
Pour garantir la compatibilité visuelle et fonctionnelle avec Visual Studio, créez des boîtes de dialogue modales pour les extensions Visual Studio en dérivant des fenêtres de boîtes de dialogue à partir de l’objet <xref:Microsoft.VisualStudio.PlatformUI.DialogWindow?displayProperty=fullName>. Les boîtes de dialogue dérivées de cette manière peuvent également fournir des fonctionnalités supplémentaires. Par exemple, vous pouvez définir des cibles Aide F1 et activer la réduction et l’agrandissement de la fenêtre.  
  
## Création de boîtes de dialogue modales  
  
1.  Dans votre projet, ajoutez une référence à System.XAML.  
  
2.  Dans l’**Explorateur de solutions**, cliquez avec le bouton droit sur le projet, cliquez sur **Ajouter**, puis sur **Fenêtre**.  
  
3.  Nommez la fenêtre, puis cliquez sur **Ajouter**.  
  
     Une fenêtre XAML vide apparaît dans le concepteur.  
  
4.  Dans l’élément `Window` de niveau supérieur, ajoutez une déclaration d’espace de noms pour <xref:Microsoft.VisualStudio.PlatformUI> et modifiez l’élément `Window` en élément <xref:Microsoft.VisualStudio.PlatformUI.DialogWindow?displayProperty=fullName>, comme indiqué dans l’exemple suivant.  
  
     [!code-xml[VSModalDialog#02](../misc/codesnippet/Xaml/extending-modal-dialog-boxes_1.xaml)]  
  
5.  Ajoutez des boutons, des étiquettes et d’autres contrôles à partir de la **Boîte à outils**, tapez les étiquettes de texte et ajustez l’apparence de la boîte de dialogue.  
  
6.  Basculez en mode code.  
  
7.  Dans la définition de classe, définissez la classe pour qu’elle hérite de <xref:Microsoft.VisualStudio.PlatformUI.DialogWindow>. \(Par défaut, la classe hérite de <xref:System.Windows.Window?displayProperty=fullName>.\)  
  
8.  Ajoutez des gestionnaires d’événements pour les boutons et autres contrôles.  
  
#### Pour ajouter l’Aide F1 à une boîte de dialogue modale  
  
1.  Ajoutez au constructeur un paramètre qui accepte une chaîne comme argument et définissez le constructeur pour qu’il hérite du constructeur de base en utilisant le même paramètre, comme indiqué dans l’exemple suivant.  
  
     [!code-cs[VSModalDialog#12](../misc/codesnippet/CSharp/extending-modal-dialog-boxes_2.cs)]  
  
     Ce constructeur affecte la valeur `true` à la propriété <xref:Microsoft.VisualStudio.PlatformUI.DialogWindowBase.HasHelpButton%2A> et permet d’utiliser la chaîne reçue comme mot clé lorsqu’un utilisateur appuie sur la touche F1 ou clique sur le bouton **Aide**.  
  
#### Pour ajouter des boutons Réduire et Agrandir à une boîte de dialogue modale  
  
1.  Dans la fonction du constructeur, affectez la valeur `true` aux propriétés <xref:Microsoft.VisualStudio.PlatformUI.DialogWindow.hasMinimizeButton%2A> et <xref:Microsoft.VisualStudio.PlatformUI.DialogWindow.hasHMaximizeButton%2A>, comme illustré dans l’exemple suivant.  
  
     [!code-cs[VSModalDialog#13](../misc/codesnippet/CSharp/extending-modal-dialog-boxes_3.cs)]  
  
    > [!WARNING]
    >  Lorsque les boutons **Réduire** et **Agrandir** sont affichés, le bouton **Aide** est masqué, même si la propriété <xref:Microsoft.VisualStudio.PlatformUI.DialogWindowBase.HasHelpButton%2A> a la valeur `true`.  
  
## Exemple  
 L’exemple suivant montre une boîte de dialogue modale qui possède deux constructeurs. Le premier constructeur accepte un mot clé F1 comme argument et affiche un bouton **Aide**. Le deuxième constructeur n’accepte aucun argument, mais il affiche des boutons **Réduire** et **Agrandir**. Lorsque vous cliquez sur le bouton **Oui**, une deuxième instance de la boîte de dialogue est appelée, dans laquelle le bouton Aide est activé.  
  
 [!code-xml[VSModalDialog#01](../misc/codesnippet/Xaml/extending-modal-dialog-boxes_4.xaml)]  
  
 [!code-cs[VSModalDialog#11](../misc/codesnippet/CSharp/extending-modal-dialog-boxes_5.cs)]  
  
 Le code suivant appelle la boîte de dialogue à partir d’un gestionnaire d’événements.  
  
 [!code-cs[VSModalDialog#21](../misc/codesnippet/CSharp/extending-modal-dialog-boxes_6.cs)]  
  
## Voir aussi  
 [Créer et gérer des boîtes de dialogue modales](../Topic/Creating%20and%20Managing%20Modal%20Dialog%20Boxes.md)