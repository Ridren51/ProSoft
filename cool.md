
Il existe plusieurs conventions de dénomination à prendre en compte lors de l'écriture du code C#.

Dans les exemples suivants, toutes les indications relatives aux éléments marqués public sont également applicables lorsque l'on travaille avec des éléments internes protégés et protégés, qui sont tous destinés à être visibles pour les appelants externes.

Cas Pascal
Utilisez la casse pascale ("PascalCasing") lorsque vous nommez une classe, un enregistrement ou une structure.

public class DataService
{
}

public record PhysicalAddress(
    chaîne Rue,
    string City,
    string StateOrProvince,
    string ZipCode) ;

public struct ValueCoordinate
{

}
Lorsque vous nommez une interface, utilisez la casse pascale en plus de préfixer le nom par un I. Cela indique clairement aux consommateurs qu'il s'agit d'une interface.

public interface IWorkerQueue
{
}
Lorsque vous nommez des membres publics de types, tels que des champs, des propriétés, des événements, des méthodes et des fonctions locales, utilisez la casse pascale.

public class ExampleEvents
{
    // Un champ public, à utiliser avec parcimonie.
    public bool IsValid ;

    // Une propriété réservée à l'init
    public IWorkerQueue WorkerQueue { get ; init ; }

    // Un événement
    public event Action EventProcessing ;

    // Méthode
    public void StartEventProcessing()
    {
        // Fonction locale
        static int CountQueueItems() => WorkerQueue.Count ;
        // ...
    }
}
Lorsque vous écrivez des enregistrements positionnels, utilisez la casse pascale pour les paramètres car ce sont les propriétés publiques de l'enregistrement.

public record PhysicalAddress(
    string Street,
    string City,
    string StateOrProvince,
    string ZipCode) ;
Pour plus d'informations sur les enregistrements positionnels, voir Syntaxe positionnelle pour la définition des propriétés.

Case camel
Utilisez la casse camel ("camelCasing") pour nommer les champs privés ou internes, et préfixez-les par _.

public class DataService
{
    private IWorkerQueue _workerQueue ;
}
Conseil Lorsque vous éditez du code C# qui suit ces conventions de dénomination dans un IDE qui prend en charge la complétion d'instructions, la saisie de _ affichera tous les membres de l'objet.

Lorsque vous travaillez avec des champs statiques qui sont privés ou internes, utilisez le préfixe s_ et pour les champs statiques de type thread, utilisez t_.

public class DataService
{
    private static IWorkerQueue s_workerQueue ;

    [ThreadStatic]
    private static TimeSpan t_timeSpan ;
}
Lorsque vous écrivez les paramètres d'une méthode, utilisez la casse camel.

public T SomeMethod<T>(int someNumber, bool isValid)
{

}
Pour plus d'informations sur les conventions d'appellation C#, voir C# Coding Style.

Conventions de nommage supplémentaires
Les exemples qui n'incluent pas de directives d'utilisation, utilisent des qualifications d'espace de noms. Si vous savez qu'un espace de noms est importé par défaut dans un projet, vous n'avez pas besoin de qualifier complètement les noms de cet espace de noms. Les noms qualifiés peuvent être brisés après un point (.) s'ils sont trop longs pour une seule ligne, comme le montre l'exemple suivant.

var currentPerformanceCounterCategory = new System.Diagnostics.
    PerformanceCounterCategory() ;
Il n'est pas nécessaire de modifier le nom des objets créés à l'aide des outils de conception de Visual Studio pour les adapter à d'autres directives.

Traduit avec www.DeepL.com/Translator (version gratuite)
