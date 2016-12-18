---
title: "Les param&#232;tres du proxy ne sont pas correctement configur&#233;s sur cet ordinateur pour la d&#233;couverte web. | Microsoft Docs"
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
  - "vs.message.VB_E_MUSTSPECIFYPROXYSERVER"
  - "vs.WebDiscoveryProxyHelp"
ms.assetid: aea2cc20-9180-47cb-b1ed-78fa5f8a407f
caps.latest.revision: 9
caps.handback.revision: 9
author: "mikeblome"
ms.author: "mblome"
manager: "douge"
---
# Les param&#232;tres du proxy ne sont pas correctement configur&#233;s sur cet ordinateur pour la d&#233;couverte web.
Cette erreur apparaît dans la boîte de dialogue Ajouter une référence web si vous développez sur un ordinateur qui se trouve derrière un pare\-feu et qu’aucun serveur proxy n’a été spécifié explicitement pour les connexions Internet Explorer. Vous devez spécifier explicitement l’adresse et le port du serveur proxy sur votre réseau pour que les services en dehors du pare\-feu soient accessibles au navigateur web dans la boîte de dialogue Ajouter une référence web. L’option de détection automatique du proxy pour les connexions Internet Explorer est ignorée par le .NET Framework. Vous devrez peut\-être demander ces informations de proxy à votre administrateur réseau.  
  
 Pour plus d’informations sur la détection automatique des clients de pare\-feu et de proxy web, consultez : [http:\/\/www.microsoft.com\/technet\/prodtechnol\/isa\/2004\/plan\/automaticdiscovery.mspx](http://www.microsoft.com/technet/prodtechnol/isa/2004/plan/automaticdiscovery.mspx)  
  
### Pour spécifier un serveur proxy pour Internet Explorer  
  
1.  Dans le menu **Outils**, choisissez **Options**.  
  
2.  Dans la boîte de dialogue **Options**, choisissez **Environnement**, puis **Navigateur web**.  
  
3.  Cliquez sur **Options d’Internet Explorer**.  
  
4.  Sous l’onglet **Connexions**, cliquez sur **Paramètres réseau**.  
  
5.  Désélectionnez **Détecter automatiquement les paramètres de connexion**.  
  
6.  Dans la zone **Serveur proxy**, sélectionnez **Utiliser un serveur proxy pour votre réseau local \(ces paramètres ne s’appliquent pas aux connexions d’accès à distance ou VPN\)**.  
  
7.  Spécifiez l’adresse et le numéro de port correspondant à votre réseau.  
  
8.  Cliquez à trois reprises sur **OK**.  
  
9. Dans le menu **Fichier**, choisissez **Quitter**, puis rouvrez Visual Studio.  
  
## Voir aussi  
 [NIB: Boîte de dialogue Ajouter une référence web](http://msdn.microsoft.com/fr-fr/bdf05776-c591-40af-bfd7-e1e2aa1e87b5)   
 [NIB: Comment ajouter et supprimer des références web](http://msdn.microsoft.com/fr-fr/a7ddaa5d-4672-405b-91b3-39de65d7e3a2)   
 [Programming the Web with XML Web Services](http://msdn.microsoft.com/fr-fr/2d651a26-73df-4b39-85fa-7913a7d6bee4)