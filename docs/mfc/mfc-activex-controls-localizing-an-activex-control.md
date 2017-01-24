---
title: "Contr&#244;les ActiveX MFC&#160;: localisation d&#39;un contr&#244;le ActiveX | Microsoft Docs"
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
  - "LocaleID"
  - "AfxOleRegisterTypeLib"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "LocaleID ambient (propriété)"
  - "localisation, contrôles ActiveX"
  - "LOCALIZE (exemple) (MFC)"
  - "contrôles ActiveX MFC, localiser"
ms.assetid: a44b839a-c652-4ec5-b824-04392708a5f9
caps.latest.revision: 12
caps.handback.revision: 9
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Contr&#244;les ActiveX MFC&#160;: localisation d&#39;un contr&#244;le ActiveX
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Cet article décrit les procédures permettant de rechercher des interfaces de contrôle ActiveX.  
  
 Si vous souhaitez faire tenir un contrôle ActiveX à un marché int, vous pouvez rechercher le contrôle.  Windows prend en charge plusieurs langues en plus de l'anglais par défaut, y compris l'Allemand, le Français, et le Suédois.  Cela peut présenter des problèmes pour le contrôle si l'interface est uniquement en anglais.  
  
 En général les contrôles ActiveX doivent toujours être basées sur les paramètres régionaux de la propriété ambiante de LocaleID.  Il y a trois manières pour effectuer cette opération :  
  
-   Chargez les ressources, toujours à la demande, en fonction de la valeur actuelle de la propriété ambiante de LocaleID.  L'exemple de [LOCALISEZ](../top/visual-cpp-samples.md) ActiveX MFC utilise cette stratégie.  
  
-   Chargez les ressources lorsque le premier contrôle est cité, selon la propriété ambiante de LocaleID, et utilisez ces ressources pour toutes les autres instances.  Cet article explique cette stratégie.  
  
    > [!NOTE]
    >  Cela ne fonctionne pas correctement dans certains cas, lorsque les instances ont des paramètres régionaux.  
  
-   Utilisez la fonction de notification de **SurAmbiantChangé** pour charger dynamiquement les ressources pertinentes pour les paramètres régionaux du conteneur.  
  
    > [!NOTE]
    >  Cela fonctionne pour le contrôle, mais la DLL d'exécution ne met pas à jour dynamiquement ses ressources propres lorsque la propriété ambiante de LocaleID change.  En outre, les DLL d'exécution pour les contrôles ActiveX utilisent les paramètres régionaux du thread pour déterminer les paramètres régionaux pour ses ressources.  
  
 Le reste de cet article décrit deux stratégies localisantes.  La première stratégie [localise l'interface de la programmabilité de contrôle](#_core_localizing_your_control.92.s_programmability_interface) \(noms des propriétés, méthodes, et les événements\).  La deuxième stratégie [localise l'interface utilisateur du contrôle](#_core_localizing_the_control.92.s_user_interface), à l'aide de la propriété ambiante de LocaleID du conteneur.  Afin de voir l'emplacement du contrôle, consultez la rubrique ActiveX MFC avec l'exemple de [LOCALISEZ](../top/visual-cpp-samples.md).  
  
##  <a name="_core_localizing_your_control.92.s_programmability_interface"></a> Rechercher l'interface de la programmabilité de contrôle  
 En recherchant l'interface de la programmabilité de contrôle \(l'interface utilisée par des programmeurs dans les applications qui utilisent votre contrôle\), vous devez créer une version modifiée du fichier .IDL de contrôle \(un script pour générer la bibliothèque de types de contrôle\) pour chaque langue que vous envisagez de prendre en charge.  Il s'agit du seul emplacement dont vous avez besoin pour rechercher les noms de propriété du contrôle.  
  
 Lorsque vous développez un contrôle localisé, incluez l'ID de paramètres régionaux comme attribut au niveau de la bibliothèque de types.  Par exemple, si vous souhaitez fournir une bibliothèque de types des noms de propriété localisée par Français, effectuez une copie de la SAMPLE.IDL classer, ainsi appelez\- la SAMPLEFR.IDL.  Ajouter un attribut ID de paramètres régionaux au fichier \(ID de paramètres régionaux pour le Français est 0x040c\), comme suit :  
  
 [!code-cpp[NVC_MFC_AxLoc#1](../mfc/codesnippet/CPP/mfc-activex-controls-localizing-an-activex-control_1.idl)]  
  
 Modifiez les noms des propriétés dans SAMPLEFR.IDL en leurs équivalents français, puis utilisez MKTYPLIB.EXE pour produire la bibliothèque de types française, SAMPLEFR.TLB.  
  
 Pour créer des bibliothèques de types traduites par plusieurs vous pouvez ajouter des fichiers situés de .IDL au projet et ils sont générés automatiquement.  
  
#### Pour ajouter un fichier .IDL à votre projet de contrôle ActiveX MFC  
  
1.  Avec un projet ouvert dans le menu de **Projet** , cliquez sur **Ajouter un élément existant**.  
  
     La boîte de dialogue **Ajouter un élément existant** s'affiche.  
  
2.  Si nécessaire, sélectionnez l'unité et le répertoire à afficher.  
  
3.  Dans la zone **Type de fichiers**, sélectionnez **Tous les fichiers \(\*.\*\)**.  
  
4.  Dans la zone de liste de fichiers, double\-cliquez sur le fichier .IDL que vous souhaitez insérer dans le projet.  
  
5.  Cliquez sur **Ouvrir** lorsque vous avez ajouté tous les fichiers nécessaires pour .IDL.  
  
 Les fichiers ont été ajoutés au projet, ils sont générés lorsque le reste du projet est généré.  Les bibliothèques de types localisées se trouvent dans le répertoire du projet actuel du contrôle ActiveX.  
  
 Dans votre code, les noms des propriétés internes \(généralement en anglais\) sont toujours utilisés et ne sont jamais localisés.  Cela inclut la table de dispatch de vérification, l'échange de propriétés s'exécute, et votre code d'échange de données de page de propriétés.  
  
 Un seul fichier de bibliothèque de types \(.TLB\) peut être liée à des ressources du fichier d'audit de l'implémentation \(.OCX\).  C'est généralement la version avec \(en général en anglais\) les noms standardisés.  Pour fournir une version localisée de votre contrôle, vous devez fournir le .OCX \(qui est déjà liée à la version de la valeur par défaut .TLB\) et le .TLB pour les paramètres régionaux appropriés.  Cela signifie que le .OCX est nécessaire pour les versions en anglais, le .TLB correct est déjà liée à celui\-ci.  Pour les autres paramètres régionaux, la bibliothèque de types localisée doit être fournie avec le .OCX.  
  
 Pour vous assurer que les clients du contrôle peuvent rechercher la bibliothèque de types localisée, enregistrez vos fichiers spécifiques aux paramètres régionaux de .TLB sous la section de typelib de Registre système Windows.  Le troisième paramètre \(normalement facultatif\) dans la fonction de [AfxOleRegisterTypeLib](../Topic/AfxOleRegisterTypeLib.md) est fourni à cet effet.  L'exemple suivant inscrit une bibliothèque de types française d'un contrôle ActiveX :  
  
 [!code-cpp[NVC_MFC_AxLoc#2](../mfc/codesnippet/CPP/mfc-activex-controls-localizing-an-activex-control_2.cpp)]  
  
 Lorsque l'audit est stocké, la fonction de `AfxOleRegisterTypeLib` recherche automatiquement le fichier spécifié de .TLB dans le même répertoire que le flux de contrôle et les stocke dans la base de données d'inscription de Windows.  Si le fichier de .TLB est introuvable, la fonction n'a aucun effet.  
  
##  <a name="_core_localizing_the_control.92.s_user_interface"></a> Rechercher l'interface utilisateur du contrôle  
 Pour rechercher l'interface utilisateur d'un contrôle, placez les ressources accessibles à l'utilisateur de tout le contrôle \(telles que les pages de propriétés et des messages d'erreur\) dans les DLL de ressource spécifiques aux langues.  Vous pouvez utiliser la propriété de ambiante LocaleID du conteneur pour sélectionner la DLL approprié pour les paramètres régionaux de l'utilisateur.  
  
 L'exemple de code suivant illustre une approche pour localiser et de charger la DLL de ressource pour les paramètres régionaux spécifiques.  Cette fonction membre, appelée `GetLocalizedResourceHandle` pour cet exemple, peut être une fonction membre de la classe de contrôle ActiveX :  
  
 [!code-cpp[NVC_MFC_AxLoc#3](../mfc/codesnippet/CPP/mfc-activex-controls-localizing-an-activex-control_3.cpp)]  
  
 Notez que l'identificateur de sous\-langue peut être signé chaque cas de échec de l'instruction, pour fournir l'emplacement version spéciale.  Afin de voir cette fonction, consultez la fonction de `GetResourceHandle` dans l'exemple de [LOCALISEZ](../top/visual-cpp-samples.md)ActiveX MFC.  
  
 Lorsque le premier de contrôle se charge dans un conteneur, il peut appeler [COleControl::AmbientLocaleID](../Topic/COleControl::AmbientLocaleID.md) pour extraire l'ID de paramètres régionaux  Le contrôle peut ensuite passer la valeur retournée de l'ID des paramètres régionaux à la fonction de `GetLocalizedResourceHandle`, qui charge la bibliothèque appropriée de ressources.  Le contrôle doit passer le descripteur obtenu, le cas échéant, à [AfxSetResourceHandle](../Topic/AfxSetResourceHandle.md):  
  
 [!code-cpp[NVC_MFC_AxLoc#4](../mfc/codesnippet/CPP/mfc-activex-controls-localizing-an-activex-control_4.cpp)]  
  
 Recherchez l'exemple de code ci\-dessus dans une fonction membre du contrôle, tel qu'une substitution de [COleControl::SurEnsembleSiteClients](../Topic/COleControl::OnSetClientSite.md).  En outre, `m_hResDLL` doit être une variable membre de la classe de contrôle.  
  
 Vous pouvez utiliser une logique similaire pour localiser la page des propriétés d'un contrôle.  Pour rechercher la page de propriétés, ajoutez l'exemple de code semblable au suivant dans le fichier d'implémentation de la page de propriétés \(dans une substitution de [COlePropertyPage::SurEnsemblePagesSites](../Topic/COlePropertyPage::OnSetPageSite.md)\) :  
  
 [!code-cpp[NVC_MFC_AxLoc#5](../mfc/codesnippet/CPP/mfc-activex-controls-localizing-an-activex-control_5.cpp)]  
  
## Voir aussi  
 [Contrôles ActiveX MFC](../mfc/mfc-activex-controls.md)