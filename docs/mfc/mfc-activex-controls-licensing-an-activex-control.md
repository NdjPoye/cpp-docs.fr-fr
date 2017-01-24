---
title: "Contr&#244;les ActiveX MFC&#160;: gestion des licences d&#39;un contr&#244;le ActiveX | Microsoft Docs"
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
  - "COleObjectFactory"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "COleObjectFactory (classe), licences des contrôles"
  - "GetLicenseKey (méthode)"
  - "licences des contrôles ActiveX"
  - "contrôles ActiveX MFC, licences"
  - "VerifyLicenseKey (méthode)"
  - "VerifyUserLicense (méthode)"
ms.assetid: cacd9e45-701a-4a1f-8f1f-b0b39f6ac303
caps.latest.revision: 10
caps.handback.revision: 6
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Contr&#244;les ActiveX MFC&#160;: gestion des licences d&#39;un contr&#244;le ActiveX
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Le support de licence, une fonctionnalité en option pour les contrôles ActiveX, vous permet de contrôler qui peut utiliser ou distribuer le contrôle. \(Pour une analyse supplémentaire des problèmes de licences de, consultez les Problèmes de Licence dans [Mettre à niveau un contrôle ActiveX existant](../mfc/upgrading-an-existing-activex-control.md).\)  
  
 Cette rubrique traite des sujets suivants :  
  
-   [Présentation de l'autorisation de contrôle ActiveX](#_core_overview_of_activex_control_licensing)  
  
-   [Création d'un contrôle de licence](#_core_creating_a_licensed_control)  
  
-   [Prise en charge des licences](#_core_licensing_support)  
  
-   [Personnalisation de licences d'un contrôle ActiveX](#_core_customizing_the_licensing_of_an_activex_control)  
  
 Les contrôles ActiveX qui implémentent les licences permettent, en tant que développeur de contrôle, de déterminer comment les autres utilisateurs utiliseront le contrôle ActiveX.  Vous fournissez à l'acheteur de contrôle le contrôle et le fichier .LIC, avec le contrat stipulant que l'acheteur peut distribuer le contrôle, mais avec pas le fichier de .LIC, avec une application qui utilise le contrôle.  Cela empêche les utilisateurs de l'application d'écrire de nouvelles applications qui utilisent le contrôle, sans vous acheter la licence de contrôle.  
  
##  <a name="_core_overview_of_activex_control_licensing"></a> Présentation de l'autorisation de contrôle ActiveX  
 Pour fournir un support de licences des contrôles ActiveX, la classe [COleObjectFactory](../mfc/reference/coleobjectfactory-class.md) fournit une implémentation pour plusieurs fonctions dans l'interface **IClassFactory2**: **IClassFactory2::RequestLicKey**, **IClassFactory2::GetLicInfo**, et **IClassFactory2::CreateInstanceLic**.  Lorsque le développeur d'application conteneur fait une demande pour créer une instance de contrôle, un appel à `GetLicInfo` est effectué pour vérifier que le fichier de contrôle .LIC est présent.  Si le contrôle est autorisé, une instance de contrôle peut être créée et placée dans le conteneur.  Une fois que le développeur a fini de construire l'application conteneur, un autre appel de fonction, cette fois à `RequestLicKey`, est effectué.  Cette fonction retourne le code licence \(une chaîne de caractères simple\) à l'application conteneur.  La clé retournée est ensuite incorporée dans l'application.  
  
 L'illustration ci\-dessous montre la vérification de licence d'un contrôle ActiveX qui sera utilisé pendant le développement d'une application conteneur.  Comme mentionné précédemment, le développeur de l'application conteneur doit avoir le fichier approprié .LIC installé sur l'ordinateur de développement pour créer une instance du contrôle.  
  
 ![Contrôle ActiveX sous licence vérifié au développement](../mfc/media/vc374d1.png "vc374D1")  
Vérification du développement de contrôle ActiveX sous licence  
  
 Le processus suivant, représenté sur l'illustration suivante, se produit lorsque l'utilisateur final exécute l'application conteneur.  
  
 Lorsque l'application démarre, une instance de contrôle à généralement besoin d'être créée.  Le conteneur réalise cette opération en faisant appel à `CreateInstanceLic`, en passant la clé de licence incorporée en tant que paramètre.  Une comparaison de chaînes est alors effectuée entre la clé de licence incorporée et la propre copie de la clé de licence du contrôle.  Si la correspondance réussit, une instance de contrôle est créée et l'application continue de s'exécuter normalement.  Notez que le fichier de .LIC n'a pas besoin d'être présent sur l'ordinateur de l'utilisateur de contrôle.  
  
 ![Contrôle ActiveX sous licence vérifié au moment de l'exécution](../mfc/media/vc374d2.png "vc374D2")  
Vérification pendant l'exécution de contrôles ActiveX sous licence  
  
 Le contrôle des licences comprend plusieurs composants de base : code spécifique dans le fichier DLL de contrôle de l'implémentation et le fichier de licence.  Le code comprend deux \(ou parfois trois\) appels de fonctions et une chaîne de caractères, ci\-dessous référencée comme « chaîne de licence », qui contient le texte de copyright.  Ces appels et la chaîne de licence se trouvent dans le fichier de contrôle de l'implémentation \(.CPP\).  Le fichier de licence, généré par l'Assistant Contrôle ActiveX, est un fichier texte avec une déclaration de copyright.  Il est nommé en utilisant le nom du projet avec une extension en .LIC, par exemple SAMPLE.LIC.  Un contrôle sous licence doit être accompagné du fichier de licence si l'utilisation de conception est nécessaire.  
  
##  <a name="_core_creating_a_licensed_control"></a> Création d'un contrôle de licence  
 Lorsque vous utilisez l'Assistant Contrôle ActiveX pour créer l'environnement de contrôle, il est facile d'y inclure la prise en charge du contrat de licence.  Lorsque vous spécifiez que le contrôle doit disposer d'une licence utilisateur, l'Assistant Contrôle ActiveX ajoute du code à la classe de contrôle pour prendre en charge la licence.  Ce code comprend des fonctions qui utilisent une clé et un fichier de licence pour la vérification de licence.  Ces fonctions peuvent également être modifiées pour personnaliser les licences de contrôle.  Pour plus d'informations sur la personnalisation de licence, consultez [Personnalisation de licences d'un contrôle ActiveX](#_core_customizing_the_licensing_of_an_activex_control) plus loin dans cet article.  
  
#### Pour ajouter la prise en charge de licence avec l'Assistant Contrôle ActiveX lorsque vous créez un projet de contrôle  
  
1.  Suivez les instructions de [Créer un contrôle ActiveX MFC](../mfc/reference/creating-an-mfc-activex-control.md).  La page **Paramètres de l'application** de l'Assistant Contrôle ActiveX contient la possibilité de créer le contrôle avec la licence utilisateur.  
  
 L'Assistant de Contrôle ActiveX génère maintenant une infrastructure de contrôle ActiveX qui inclut la prise en charge de base du contrat de licence.  Pour une explication détaillée du code de licence, consultez la rubrique suivante.  
  
##  <a name="_core_licensing_support"></a> Prise en charge des licences  
 Lorsque vous utilisez l'Assistant Contrôle ActiveX pour ajouter la prise en charge du contrat de licence à un contrôle ActiveX, l'Assistant Contrôle ActiveX ajoute le code qui déclare et implémente la fonctionnalité du contrat de licence à l'en\-tête de contrôle et aux fichiers d'implémentation.  Ce code est composé d'une fonction membre `VerifyUserLicense` et d'une fonction membre `GetLicenseKey`, qui remplacent les implémentations par défaut présentes dans [COleObjectFactory](../mfc/reference/coleobjectfactory-class.md).  Les fonctions suivantes extraient et vérifient la licence de contrôle.  
  
> [!NOTE]
>  Une troisième fonction membre, `VerifyLicenseKey` n'est pas générée par l'Assistant Contrôle ActiveX, mais elle peut être remplacée pour personnaliser le comportement de la vérification du code licence.  
  
 Ces fonctions membres sont:  
  
-   [VerifyUserLicense](../Topic/COleObjectFactory::VerifyUserLicense.md)  
  
     Vérifie que le contrôle permette l'utilisation de conception en vérifiant le système pour la présence du fichier de licence de contrôle.  Cette fonction est appelée par l'environnement dans le cadre du traitement **IClassFactory2::GetLicInfo** et **IClassFactory::CreateInstanceLic**.  
  
-   [GetLicenseKey](../Topic/COleObjectFactory::GetLicenseKey.md)  
  
     Demande une clé unique à la DLL de contrôle.  Cette clé est incorporée dans l'application conteneur et utilisée ultérieurement, en conjonction avec `VerifyLicenseKey`, pour créer une instance du contrôle.  Cette fonction est appelée par l'environnement dans le cadre du traitement **IClassFactory2::RequestLicKey**.  
  
-   [VerifyLicenseKey](../Topic/COleObjectFactory::VerifyLicenseKey.md)  
  
     Vérifie que la clé incorporée et la clé unique de contrôle sont identiques.  Cela autorise le conteneur de créer une instance de contrôle pour son usage.  Cette fonction est appelée par l'environnement dans le cadre du traitement **IClassFactory2::CreateInstanceLic** et peut être remplacée pour fournir une vérification personnalisée du code licence.  L'implémentation par défaut effectue une comparaison de chaînes.  Pour plus d'informations, consultez [Personnalisation de licences d'un contrôle ActiveX](#_core_customizing_the_licensing_of_an_activex_control), plus loin dans cet article.  
  
###  <a name="_core_header_file_modifications"></a> Modifications du fichier d'en\-tête  
 Assistant Contrôle ActiveX place le code suivant dans le fichier d'en\-tête de contrôle.  Dans cet exemple, deux fonctions membres de l'objet `factory` de `CSampleCtrl`sont déclarées, une qui vérifie la présence du fichier de contrôle .LIC et une autre qui récupère le code licence à utiliser dans l'application contenant le contrôle :  
  
 [!code-cpp[NVC_MFC_AxUI#39](../mfc/codesnippet/CPP/mfc-activex-controls-licensing-an-activex-control_1.h)]  
  
###  <a name="_core_implementation_file_modifications"></a> Modifications du fichier d'implémentation  
 Assistant Contrôle ActiveX place les deux instructions suivantes dans le fichier d'implémentation du contrôle pour déclarer le nom de fichier de licence et la chaîne de licence :  
  
 [!code-cpp[NVC_MFC_AxUI#40](../mfc/codesnippet/CPP/mfc-activex-controls-licensing-an-activex-control_2.cpp)]  
  
> [!NOTE]
>  Si vous modifiez **szLicString** de quelque manière, vous devez également modifier la première ligne du fichier du contrôle .LIC ou l'autorisation de licence ne fonctionnera pas correctement.  
  
 Assistant Contrôle ActiveX place le code suivant dans le fichier d'implémentation du contrôle pour définir les classes de contrôle `VerifyUserLicense` ainsi que les fonctions `GetLicenseKey`:  
  
 [!code-cpp[NVC_MFC_AxUI#41](../mfc/codesnippet/CPP/mfc-activex-controls-licensing-an-activex-control_3.cpp)]  
  
 Enfin, **Assistant Contrôle ActiveX** modifie le fichier .IDL de projet de contrôle.  Le mot clé **licence** est ajouté à la déclaration de coclasse de contrôle, comme dans l'exemple suivant :  
  
 [!code-cpp[NVC_MFC_AxUI#42](../mfc/codesnippet/CPP/mfc-activex-controls-licensing-an-activex-control_4.idl)]  
  
##  <a name="_core_customizing_the_licensing_of_an_activex_control"></a> Personnalisation de licences d'un contrôle ActiveX  
 Comme `VerifyUserLicense`, `GetLicenseKey`, et `VerifyLicenseKey` sont déclarés en tant que fonctions membres virtuelles de la classe de fabrique de contrôle, vous pouvez personnaliser le comportement de licences du contrôle.  
  
 Par exemple, vous pouvez fournir plusieurs niveaux de licences pour contrôle en remplaçant les fonctions membres `VerifyUserLicense` ou `VerifyLicenseKey`.  Dans cette fonction vous pouvez régler quelles propriétés ou méthodes sont exposées à l'utilisateur selon le niveau de licence que vous avez détecté.  
  
 Vous pouvez également ajouter du code à la fonction `VerifyLicenseKey` qui fournit une méthode personnalisée pour avertir l'utilisateur que la création de contrôle a échoué.  Par exemple, dans votre fonction membre `VerifyLicenseKey` vous pouvez afficher un message dans une boîte de dialogue indiquant que le contrôle n'a pas été initialisé et pourquoi.  
  
> [!NOTE]
>  Une autre façon de personnaliser la vérification de licence du contrôle ActiveX consiste à vérifier l'enregistrement de la base de données pour une clé de registre spécifique, au lieu d'appeler `AfxVerifyLicFile`.  Pour obtenir un exemple de l'implémentation par défaut, consultez la section [Modifications du fichier d'implémentation](#_core_implementation_file_modifications) de cet article.  
  
 \(Pour une analyse supplémentaire des problèmes de licences, consultez les Problèmes de Licence dans [Mettre à niveau un contrôle ActiveX existant](../mfc/upgrading-an-existing-activex-control.md).\)  
  
## Voir aussi  
 [Contrôles ActiveX MFC](../mfc/mfc-activex-controls.md)   
 [Contrôle ActiveX MFC \(Assistant\)](../mfc/reference/mfc-activex-control-wizard.md)