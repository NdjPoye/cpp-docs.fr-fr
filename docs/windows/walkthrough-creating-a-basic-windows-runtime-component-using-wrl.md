---
title: "Proc&#233;dure pas &#224; pas&#160;: cr&#233;ation d&#39;un composant Windows Runtime de base &#224; l&#39;aide de WRL | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
dev_langs: 
  - "C++"
ms.assetid: 6e3f0986-7905-4f94-90e5-22c2ebfc8cd0
caps.latest.revision: 9
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 9
---
# Proc&#233;dure pas &#224; pas&#160;: cr&#233;ation d&#39;un composant Windows Runtime de base &#224; l&#39;aide de WRL
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Ce document montre comment utiliser le [!INCLUDE[cppwrl](../windows/includes/cppwrl_md.md)] ([!INCLUDE[cppwrl_short](../windows/includes/cppwrl_short_md.md)]) pour créer un base [!INCLUDE[wrt](../atl/reference/includes/wrt_md.md)] composant. Le composant ajoute deux nombres et déclenche un événement lorsque le résultat est un nombre premier. Ce document montre également comment utiliser le composant d’un [!INCLUDE[win8_appname_long](../build/includes/win8_appname_long_md.md)] application qui utilise JavaScript.  
  
## <a name="prerequisites"></a>Prérequis  
  
-   Expérience avec les [Windows Runtime](http://msdn.microsoft.com/library/windows/apps/br211377.aspx).  
  
-   Expérience avec COM.  
  
### <a name="to-create-a-basic-includewrttokenwrtmdmd-component-that-adds-two-numbers"></a>Pour créer un base [!INCLUDE[wrt](../atl/reference/includes/wrt_md.md)] composant qui ajoute deux nombres  
  
1.  Dans Visual Studio, créez un Visual C++ `WRLClassLibrary` projet. Le document [modèle de projet bibliothèque de classes](../windows/wrl-class-library-project-template.md) décrit comment télécharger ce modèle. Attribuez un nom au projet `Contoso`.  
  
2.  Dans Contoso.cpp et Contoso.idl, remplacez toutes les instances de « WinRTClass » avec « Calculator ».  
  
3.  Dans Contoso.idl, ajoutez le `Add` méthode à la `ICalculator` interface.  
  
     [!code-cpp[wrl-basic-component#1](../windows/codesnippet/CPP/walkthrough-creating-a-basic-windows-runtime-component-using-wrl_1.idl)]  
  
4.  Dans Contoso.cpp, ajoutez le `Add` méthode à la `public` section de la `Calculator` classe.  
  
     [!code-cpp[wrl-basic-component#2](../windows/codesnippet/CPP/walkthrough-creating-a-basic-windows-runtime-component-using-wrl_2.cpp)]  
  
    > [!IMPORTANT]
    >  Étant donné que vous créez un composant COM, n’oubliez pas d’utiliser le `__stdcall` convention d’appel.  
  
     Nous vous recommandons d’utiliser `_Out_` et d’autres annotations de langage (SAL) source d’annotation pour décrire la façon dont une fonction utilise ses paramètres. Les annotations SAL permettent également de décrire des valeurs de retour. Les annotations SAL fonctionnent avec le [outil d’analyse du Code C/C++](../Topic/Code%20Analysis%20for%20C-C++%20Overview.md) pour détecter les erreurs possibles dans C et C++ de code source. Les erreurs de codage courantes signalées par l’outil sont les dépassements de mémoire tampon, mémoire non initialisée, déréférence du pointeur null et les fuites de mémoire et ressources.  
  
### <a name="to-use-the-component-from-a-includewin8appnamelongtokenwin8appnamelongmdmd-app-that-uses-javascript"></a>Pour utiliser le composant d’un [!INCLUDE[win8_appname_long](../build/includes/win8_appname_long_md.md)] application qui utilise du code JavaScript  
  
1.  Dans Visual Studio, ajoutez un nouveau code JavaScript `Blank App` projet à la `Contoso` solution. Attribuez un nom au projet `CalculatorJS`.  
  
2.  Dans la `CalculatorJS` de projet, ajoutez une référence à la `Contoso` projet.  
  
3.  Dans le fichier default.html, remplacez la `body` section avec ces éléments d’interface Utilisateur :  
  
     [!code-html[wrl-basic-component#3](../windows/codesnippet/Html/walkthrough-creating-a-basic-windows-runtime-component-using-wrl_3.html)]  
  
4.  Dans default.js, implémentez le `OnClick` (fonction).  
  
     [!code-javascript[wrl-basic-component#4](../windows/codesnippet/JavaScript/walkthrough-creating-a-basic-windows-runtime-component-using-wrl_4.js)]  
  
    > [!NOTE]
    >  Dans JavaScript, la première lettre du nom de la méthode est en minuscule pour respecter les conventions d’affectation de noms standards.  
  
### <a name="to-add-an-event-that-fires-when-a-prime-number-is-calculated"></a>Pour ajouter un événement qui se déclenche lorsqu’un nombre premier est calculé.  
  
1.  Dans Contoso.idl, avant la déclaration de `ICalculator`, définissez le type délégué, `PrimeNumberEvent`, qui fournit un `int` argument.  
  
     [!code-cpp[wrl-basic-component#5](../windows/codesnippet/CPP/walkthrough-creating-a-basic-windows-runtime-component-using-wrl_5.idl)]  
  
     Lorsque vous utilisez la `delegate` (mot clé), le compilateur MIDL crée une interface qui contient un `Invoke` méthode qui correspond à cette signature de délégué. Dans cet exemple, le fichier généré Contoso_h.h définit le `IPrimeNumberEvent` interface, qui est utilisé ultérieurement dans cette procédure.  
  
     [!code-cpp[wrl-basic-component#13](../windows/codesnippet/CPP/walkthrough-creating-a-basic-windows-runtime-component-using-wrl_6.cpp)]  
  
2.  Dans la `ICalculator` de l’interface, définissez la `PrimeNumberFound` événement. Le `eventadd` et `eventremove` attributs spécifient que le consommateur de la `ICalculator` interface peut s’abonner à et annuler l’abonnement à cet événement.  
  
     [!code-cpp[wrl-basic-component#6](../windows/codesnippet/CPP/walkthrough-creating-a-basic-windows-runtime-component-using-wrl_7.idl)]  
  
3.  Dans Contoso.cpp, ajoutez un `private` [Microsoft::WRL::EventSource](../windows/eventsource-class.md) variable de membre pour gérer les abonnés aux événements et appeler le Gestionnaire d’événements.  
  
     [!code-cpp[wrl-basic-component#7](../windows/codesnippet/CPP/walkthrough-creating-a-basic-windows-runtime-component-using-wrl_8.cpp)]  
  
4.  Dans Contoso.cpp, implémentez le `add_PrimeNumberFound` et `remove_PrimeNumberFound` méthodes.  
  
     [!code-cpp[wrl-basic-component#8](../windows/codesnippet/CPP/walkthrough-creating-a-basic-windows-runtime-component-using-wrl_9.cpp)]  
  
### <a name="to-raise-the-event-when-a-prime-number-is-calculated"></a>Pour déclencher l’événement lorsqu’un nombre premier est calculée.  
  
1.  Dans Contoso.cpp, ajoutez le `IsPrime` méthode à la `private` section de la `Calculator` classe.  
  
     [!code-cpp[wrl-basic-component#12](../windows/codesnippet/CPP/walkthrough-creating-a-basic-windows-runtime-component-using-wrl_10.cpp)]  
  
2.  Modifier la `Calculator`de `Add` méthode à appeler le [Microsoft::WRL::EventSource::InvokeAll](../windows/eventsource-invokeall-method.md) méthode lors du calcul d’un nombre premier.  
  
     [!code-cpp[wrl-basic-component#11](../windows/codesnippet/CPP/walkthrough-creating-a-basic-windows-runtime-component-using-wrl_11.cpp)]  
  
### <a name="to-handle-the-event-from-javascript"></a>Pour gérer l’événement à partir de JavaScript  
  
1.  Dans le fichier default.html, modifiez la `body` section d’inclure une zone de texte qui contient les nombres premiers.  
  
     [!code-html[wrl-basic-component#9](../windows/codesnippet/Html/walkthrough-creating-a-basic-windows-runtime-component-using-wrl_12.html)]  
  
2.  Dans default.js, modifiez le `Add` (fonction) pour gérer les `PrimeNumberFound` événement. Le Gestionnaire d’événements ajoute le nombre de premiers à la zone de texte qui a été définie à l’étape précédente.  
  
     [!code-javascript[wrl-basic-component#10](../windows/codesnippet/JavaScript/walkthrough-creating-a-basic-windows-runtime-component-using-wrl_13.js)]  
  
    > [!NOTE]
    >  Dans JavaScript, les noms d’événements sont changés en minuscules et sont précédées de « on » pour respecter les conventions d’affectation de noms standards.  
  
 L’illustration suivante montre l’application Calculatrice de base.  
  
 ![Application Calculatrice de base utilisant JavaScript](../windows/media/wrl_basic_component.png "WRL_Basic_Component")  
  
## <a name="next-steps"></a>Étapes suivantes  
  
## <a name="see-also"></a>Voir aussi  
 [Windows Runtime bibliothèque de modèles C++ (WRL)](../windows/windows-runtime-cpp-template-library-wrl.md)   
 [Modèle de projet bibliothèque de classes](../windows/wrl-class-library-project-template.md)   
 [Outil d’analyse du Code C/C++](../Topic/Code%20Analysis%20for%20C-C++%20Overview.md)