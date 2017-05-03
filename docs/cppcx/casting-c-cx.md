---
title: "Effectuer un cast (C++/CX) | Microsoft Docs"
ms.custom: ""
ms.date: "12/30/2016"
ms.prod: "windows-client-threshold"
ms.technology: ""
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 5247f6c7-6a0a-4021-97c9-21c868bd9455
caps.latest.revision: 15
author: "ghogen"
ms.author: "ghogen"
manager: "ghogen"
caps.handback.revision: 15
---
# Effectuer un cast (C++/CX)
Quatre opérateurs de cast différents s'appliquent aux types [!INCLUDE[wrt](../cppcx/includes/wrt-md.md)] : [opérateur static\_cast](../cpp/static-cast-operator.md), [opérateur dynamic\_cast](../cpp/dynamic-cast-operator.md), [opérateur safe\_cast](../Topic/safe_cast%20\(C++%20Component%20Extensions\).md) et [opérateur reinterpret\_cast](../cpp/reinterpret-cast-operator.md).`safe_cast` et `static_cast` lèvent une exception lorsque la conversion ne peut pas être exécutée. L'[opérateur static\_cast](../cpp/static-cast-operator.md) effectue également une vérification de type au moment de la compilation.`dynamic_cast` retourne `nullptr` s'il ne réussit pas à convertir le type. Même si `reinterpret_cast` retourne une valeur non null, elle peut ne pas être valide. C'est la raison pour laquelle nous vous recommandons de ne pas utiliser `reinterpret_cast`, sauf si vous savez que le cast va réussir. De même, nous vous recommandons de ne pas utiliser de casts de style C dans votre code d'[!INCLUDE[cppwrt](../cppcx/includes/cppwrt-md.md)] \([!INCLUDE[cppwrt_short](../cppcx/includes/cppwrt-short-md.md)]\) car ils sont identiques à `reinterpret_cast`.  
  
 Le compilateur et le runtime exécutent également des casts implicites, par exemple, dans les opérations de boxing lorsqu'un type valeur ou un type intégré sont passés en tant qu'arguments à une méthode dont le type de paramètre est `Object^`. En théorie, un cast implicite ne doit jamais générer une exception au moment de l'exécution. Si le compilateur ne peut pas effectuer une conversion implicite, il déclenche une erreur au moment de la compilation.  
  
 [!INCLUDE[cppwrt](../cppcx/includes/cppwrt-md.md)] sont des abstractions sur COM, qui utilisent les codes d'erreur HRESULT au lieu des exceptions. En général, [Platform::InvalidCastException](../cppcx/platform-invalidcastexception-class.md) indique une erreur COM de bas niveau d'E\_NOINTERFACE.  
  
## static\_cast  
 `static_cast` est vérifié au moment de la compilation pour déterminer s'il existe une relation d'héritage entre les deux types. Le cast provoque une erreur de compilation si les types ne sont pas liés.  
  
 `static_cast` sur une classe ref entraîne également une vérification au moment de l'exécution.`static_cast` sur une classe de référence peut passer la vérification du moment de compilation mais encore échouer au moment de l'exécution. Dans ce cas, `Platform::InvalidCastException` est levée. En général, vous n'avez pas à gérer ces exceptions, car elles indiquent presque toujours des erreurs de programmation que vous pouvez éliminer au cours du développement et des tests.  
  
 Utilisez `static_cast` si le code déclare explicitement une relation entre les deux types, et si vous êtes certain que le cast doit fonctionner.  
  
```  
interface class A{}; public ref class Class1 sealed : A { }; ... A^ obj = ref new Class1(); // Class1 is an A // You know obj is a Class1. The compiler verifies that this is possible, and in C++/CX a run-time check is also performed. Class1^ c = static_cast<Class1^>(obj);  
  
```  
  
## safe\_cast  
 L'opérateur `safe_cast` fait partie des [!INCLUDE[cppwrt](../cppcx/includes/cppwrt-md.md)]. Il effectue une vérification de type au moment de l'exécution et lève une `Platform::InvalidCastException` si la conversion échoue. Utilisez `safe_cast` lorsqu'une défaillance au moment de l'exécution indique une condition exceptionnelle. L'objectif principal de `safe_cast` est d'aider à identifier les erreurs de programmation au cours des phases de développement et de test au point où elles se produisent. Vous ne devez pas gérer l'exception, car l'exception non gérée elle\-même identifie le point de défaillance.  
  
 Utilisez safe\_cast si le code ne déclare pas la relation mais que vous avez la certitude que le cast doit fonctionner.  
  
```  
  
// A and B are not related interface class A{}; interface class B{}; public ref class Class1 sealed : A, B { }; ... A^ obj = ref new Class1(); // You know that obj’s backing type implements A and B, but // the compiler can’t tell this by comparing A and B. The run-time type check succeeds. B^ obj2 = safe_cast<B^>(obj);  
  
```  
  
## dynamic\_cast  
 Utilisez `dynamic_cast` lorsque vous effectuez un cast d'un objet \(plus spécifiquement, un chapeau« ^ »\) en un type plus dérivé, vous vous attendez à ce que l'objet cible soit parfois `nullptr` ou que le cast puisse échouer, et vous souhaitez gérer cette condition comme un chemin de code normal au lieu d'une exception. Par exemple, dans le modèle de projet d'**Application vide du Windows Store**, la méthode `OnLaunched` dans `app.xamp.cpp` utilise `dynamic_cast` pour tester si la fenêtre d'application possède du contenu. Ce n'est pas une erreur si elle ne possède pas de contenu mais une condition attendue.`Windows::Current::Content` est un `Windows::UI::XAML::UIElement` et est converti en un `Windows::UI.XAML::Controls::Frame`, qui est un type plus dérivé dans la hiérarchie d'héritage.  
  
```  
void App::OnLaunched(Windows::ApplicationModel::Activation::LaunchActivatedEventArgs^ args) { auto rootFrame = dynamic_cast<Frame^>(Window::Current->Content); // Do not repeat app initialization when the window already has content, // just ensure that the window is active if (rootFrame == nullptr) { // Create a Frame to act as the navigation context and associate it with // a SuspensionManager key rootFrame = ref new Frame(); ...  
```  
  
 Une autre utilisation de `dynamic_cast` est de détecter un `Object^` pour déterminer s'il contient un type valeur boxed. Dans ce cas, vous tentez une `dynamic_cast<Platform::Box>` ou une `dynamic_cast<Platform::IBox>`.  
  
 **dynamic\_cast et références de suivi \(%\)**  
  
 Vous pouvez également appliquer un `dynamic_cast` à une référence de suivi, mais dans ce cas, le cast se comporte comme un `safe_cast`. Il lève une `Platform::InvalidCastException` en cas d'échec, car une référence de suivi ne peut pas avoir la valeur `nullptr`.  
  
## reinterpret\_cast  
 Nous vous recommandons de ne pas utiliser [reinterpret\_cast](../cpp/reinterpret-cast-operator.md), car aucune vérification n'est effectuée, que ce soit au moment de la compilation ou de l'exécution. Dans le pire des cas, si `reinterpret_cast` est utilisé, certaines erreurs de programmation risquent de ne pas être détectées au moment du développement, ce qui peut entraîner des dysfonctionnements \(mineurs ou majeurs\) de votre programme. Par conséquent, nous vous recommandons d'utiliser `reinterpret_cast` uniquement dans les rares cas où vous devez effectuer un cast entre des types non liés et vous savez que le cast réussit. La conversion d'un type d'[!INCLUDE[cppwrt](../cppcx/includes/cppwrt-md.md)] en son type ABI sous\-jacent est rarement utilisée. Elle signifie que vous prenez le contrôle du décompte de références pour l'objet. C'est la raison pour laquelle nous vous recommandons d'utiliser le pointeur intelligent [ComPtr, classe](../windows/comptr-class.md). Sinon, vous devez appeler spécifiquement Release sur l'interface. L'exemple suivant montre comment une classe de référence peut faire l'objet d'un cast en une `IInspectable*`.  
  
```  
  
#include <wrl.h> using namespace Microsoft::WRL; auto winRtObject = ref new SomeWinRTType(); ComPtr<IInspectable> inspectable = reinterpret_cast<IInspectable*>(obj2); ...  
  
```  
  
 Si vous utilisez `reinterpret_cast` pour convertir d'une interface d'[!INCLUDE[cppwrt](../cppcx/includes/cppwrt-md.md)] à une autre, vous conduisez l'objet à être libéré deux fois. Par conséquent, utilisez uniquement ce cast lorsque vous convertissez en une interface autre que d'[!INCLUDE[cppwrt](../cppcx/includes/cppwrt-md.md)].  
  
 **Types ABI.**  
  
-   Les types ABI se trouvent dans les en\-têtes du Kit de développement logiciel \(SDK\) Windows. Pour des raisons de commodité, les en\-têtes sont nommés d'après le nom des espaces de noms, par exemple, `windows.storage.h`.  
  
-   Les types ABI se trouvent dans une ABI d'espace de noms spéciale, par exemple, `ABI::Windows::Storage::Streams::IBuffer*`.  
  
-   Les conversions entre un type d'interface d'[!INCLUDE[cppwrt](../cppcx/includes/cppwrt-md.md)] et son type ABI équivalent sont toujours sécurisées, c'est\-à\-dire d'`IBuffer^` en `ABI::IBuffer*`.  
  
-   Une classe d'exécution [!INCLUDE[cppwrt](../cppcx/includes/cppwrt-md.md)] doit toujours être convertie en `IInspectable*` ou en son interface par défaut, si cela est connu.  
  
-   Après la conversion en types ABI, vous possédez la durée de vie du type et vous devez suivre les règles COM. Nous vous recommandons d'utiliser `WRL::ComPtr` pour simplifier la gestion de la durée de vie des pointeurs ABI.  
  
 Le tableau suivant récapitule les cas dans lesquels il est possible d'utiliser `reinterpret_cast` en toute sécurité. Dans tous les cas, le cast est sécurisé dans les deux sens.  
  
|||  
|-|-|  
|HSTRING|String^|  
|HSTRING\*|String^\*|  
|IInspectable\*|Object^|  
|IInspectable\*\*|Object^\*|  
|IInspectable\-derived\-type\*|same\-interface\-from\-winmd^|  
|IInspectable\-derived\-type\*\*|same\-interface\-from\-winmd^\*|  
|IDefault\-interface\-of\-RuntimeClass\*|same\-RefClass\-from\-winmd^|  
|IDefault\-interface\-of\-RuntimeClass\*\*|same\-RefClass\-from\-winmd^\*|  
  
## Voir aussi  
 [système de type](../cppcx/type-system-c-cx.md)   
 [Référence du langage Visual C\+\+](../cppcx/visual-c-language-reference-c-cx.md)   
 [Référence aux espaces de noms](../cppcx/namespaces-reference-c-cx.md)