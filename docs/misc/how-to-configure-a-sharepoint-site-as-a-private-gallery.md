---
title: "Comment&#160;: configurer un site SharePoint en tant que galerie priv&#233;e | Microsoft Docs"
ms.custom: ""
ms.date: "11/16/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-csharp"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "SharePoint, galeries privées"
  - "galeries privées, Sharepoint"
ms.assetid: 6c6ed45f-7e46-4ed0-8b5c-839dbbe3769f
caps.latest.revision: 9
caps.handback.revision: 9
manager: "douge"
---
# Comment&#160;: configurer un site SharePoint en tant que galerie priv&#233;e
Vous pouvez créer une page de liste SharePoint qui décrit et fournit des extensions dans une galerie privée et ajouter la liste à **Extensions et mises à jour**. Pour plus d'informations, consultez [Les galeries privées](../Topic/Private%20Galleries.md).  
  
 Pour utiliser SharePoint pour créer une galerie privée  
  
1.  Tout d’abord, créez une page de liste pour la galerie privée.  
  
2.  Ensuite, chargez les fichiers d’extension \(.vsix\) en tant qu’éléments sur la page de liste.  
  
> [!IMPORTANT]
>  Pour des raisons de sécurité, SharePoint bloque le chargement des fichiers .vsix. Quand vous configurez une galerie privée, assurez\-vous que les fichiers .vsix ne sont pas bloqués. Pour plus d’informations, consultez [Gérer les types de fichiers bloqués](http://go.microsoft.com/fwlink/?LinkID=201253).  
  
## Création d’une page de liste pour une galerie privée  
 Selon la configuration des serveurs SharePoint vers lesquels vous effectuez un déploiement, les étapes suivantes peuvent varier. En général, ces instructions de déploiement sont les mêmes pour toute extension WSP pour SharePoint. Pour obtenir une explication de l’outil STSAdm, qui peut être utilisé pour la gestion des déploiements de solutions SharePoint, consultez [Déploiement de solutions avec SharePoint 2007](http://go.microsoft.com/fwlink/?LinkId=220676) sur le site web MSDN Magazine.  
  
#### Pour créer une page de liste pour une galerie privée  
  
1.  Chargez le fichier Visual Studio Extensions List \(.wsp\) sur le serveur SharePoint.  
  
2.  À l’invite de commandes, exécutez les commandes suivantes pour installer le fichier .wsp sur le serveur SharePoint.  
  
     **stsadm –o addsolution –name VisualStudioExtensionsList.wsp**  
  
     **stsadm –o deploysolution –name VisualStudioExtensionsList.wsp –url http:\/\/\<SERVERNAME\> –allowCasPolicies –allowgacdeployment –immediate**  
  
     Peut\-être devez\-vous également activer la fonctionnalité par le biais de l’interface utilisateur SharePoint pour un sous\-site, comme suit.  
  
    1.  Dans la barre de menus, choisissez **Actions du site**, **Paramètres du site**, **Gérer les fonctionnalités du site**.  
  
    2.  Choisissez le bouton **Activer** situé en regard de **Bibliothèque d’extensions Visual Studio**.  
  
    3.  Ajoutez la bibliothèque d’extensions Visual Studio au sous\-site souhaité.  
  
 Si vous devez supprimer une page de liste, procédez comme suit.  
  
#### Pour supprimer une page de liste pour une galerie privée  
  
1.  À l’invite de commandes, exécutez les commandes suivantes pour supprimer le fichier .wsp sur le serveur SharePoint.  
  
     **stsadm –o retractsolution –name VisualStudioExtensionsList.wsp –immediate**  
  
     **stsadm –o deletesolution –name VisualStudioExtensionsList.wsp**  
  
2.  Dans SharePoint, rétractez et supprimez la solution.  
  
## FAQ  
  
### Que se passe\-t\-il quand une extension est chargée ?  
 Quand un fichier d’extension \(.vsix\) Visual Studio est chargé, des informations sont extraites de ce fichier. Tout d’abord, certaines valeurs provenant du fichier .vsixmanifest incorporé, par exemple, VsixId, VsixVersion, etc. sont extraites et stockées sous forme de valeurs de métadonnées masquées sur le SPListItem correspondant. Ensuite, les fichiers Icon et PreviewImage de l’extension sont extraits et stockés dans une liste distincte.  
  
 Les images sont stockées dans les bibliothèques d’images nommées *ListTitle*\_VSIXIcons et *ListTitle*\_VSIXPreviewImages, où *ListTitle* est le nom de l’instance de liste qui stocke les fichiers .vsix. Le nom de chaque fichier image reçoit l’ID VSIX correspondant en tant que préfixe.  
  
### Que se passe\-t\-il quand une extension est supprimée ?  
 Quand un fichier .vsix est supprimé, les fichiers image correspondants \(le cas échéant\) le sont également.  
  
### Que se passe\-t\-il quand une extension est mise à jour ?  
 Une extension peut être mise à jour en chargeant une nouvelle version du fichier .vsix et en écrasant la version existante. Quand une extension est mise à jour, toutes les valeurs de métadonnées et images de l’extension sont mises à jour selon les valeurs de la nouvelle version.  
  
### Que se passe\-t\-il quand une liste est supprimée ?  
 Quand une instance d’une liste d’extensions Visual Studio est supprimée, les bibliothèques d’images \_VSIXIcons et \_VSIXPreviewImages correspondantes le sont également.  
  
### Quelles sont les versions de SharePoint prises en charge ?  
 À l’heure actuelle, seul SharePoint 2010 est pris en charge.  
  
## Voir aussi  
 [Les galeries privées](../Topic/Private%20Galleries.md)