---
title: "Diagnostic des erreurs d&#39;activation des applications du d&#233;bogueur | Microsoft Docs"
ms.custom: ""
ms.date: "10/29/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-csharp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "vs.debug.error.app_activation_failure"
dev_langs: 
  - "FSharp"
  - "VB"
  - "CSharp"
  - "C++"
ms.assetid: 558ddc6d-0952-4617-84b8-0838717febcc
caps.latest.revision: 11
caps.handback.revision: 11
ms.author: "susanno"
manager: "douge"
---
# Diagnostic des erreurs d&#39;activation des applications du d&#233;bogueur
Vous pouvez obtenir l'une des erreurs suivantes lorsque vous essayez de démarrer une application Windows Store dans le débogueur Visual Studio :  
  
 **8061**  
  
```  
Unable to activate Windows Store app 'AppName'. The ProcessName process started, but the activation request failed with error 'ErrorNumber'  
```  
  
 **8062**  
  
```  
Unable to activate Windows Store app 'AppName'. The activation request failed with error 'ErrorNumber'  
```  
  
## Pour diagnostiquer les erreurs  
 Il n'existe aucune façon sécurisée de résoudre ces erreurs.  Utilisez ces techniques pour diagnostiquer le problème.  
  
### Utiliser l'Observateur d'événements  
  
1.  Ouvrir l'observateur d'événements \(dans le menu Démarrer de Windows, recherchez **Observateur d'événements**\).  Dans l'Observateur d'événements, naviguez dans l'arborescence jusqu'au dossier **Application and Services Log\\Microsoft\\Windows\\Apps**.  
  
2.  Filtrer la vue en fonction des ID d'événement : 5900\-6000  
  
3.  Examinez le journal et voyez ce qui s'est produit.  
  
### Utiliser le débogueur natif  
 Configurez le projet à exécuter sous un débogueur natif.  
  
 Dans Visual Studio, affectez **Type de débogueur** à **Natif uniquement** sur la page **Déboguer** \(**Débogage** en C\+\+ et JavaScript\) des pages de propriétés du projet de démarrage.  
  
 Examinez les exceptions levées en examinant la fenêtre de sortie.  Vous pouvez configurer le débogueur de façon à ce qu'il s'arrête lorsque ces exceptions sont levées.  
  
## Correction des erreurs de licence d'application  
 Vous pouvez obtenir une erreur d'activation contenant « Échec du lancement de cette application en raison d’un problème de licence ». Vous pouvez essayer ces solutions de contournement :  
  
-   Dans le menu **Générer**, choisissez **Nettoyer la solution**, ouvrez le dossier de la solution dans l'Explorateur de fichiers et supprimez les dossiers **bin** et **obj**.  Ensuite, choisissez **Générer**, **Regénérer la solution**.  La regénération de la solution recrée les dossiers nécessaires.  
  
-   Sélectionnez l'application dans l'écran d'accueil, puis choisissez Désinstaller dans la barre d'application.  Nettoyez et regénérez votre solution.  
  
-   À partir d'une invite de commandes exécutée avec des privilèges d'administrateur, utilisez des commandes PowerShell pour supprimer et réinstaller votre licence de développeur.  Nettoyez et regénérez votre solution.  Voir [Obtention d’une licence de développeur à partir d’une invite de commandes](http://msdn.microsoft.com/library/windows/apps/Hh974578.aspx#getting_a_developer_license_at_a_command_prompt).