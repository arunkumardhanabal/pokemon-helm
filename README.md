# Pokémon Data Fetcher Deployment

This guide outlines how to deploy and run the Pokémon Data Fetcher application on a Kubernetes cluster using Helm and execute the script.

## Prerequisites

* Helm installed
* Minikube installed

## Steps

1.  **Clone the repository:**

    ```bash
    git clone (https://github.com/arunkumardhanabal/pokemon-helm.git)
    ```

2.  **Install the Helm chart:**

    ```bash
    helm install my-release pokemon-helm
    ```
    
3.  **Execute the Python script in the pod:**

    * Identify the name of the pod where your application is running. You can find this using:

        ```bash
        kubectl get pods
        ```

    * The pod name will likely be something like `pokemon-app-xxxxx-yyyyy`.  Let's assume it's `pokemon-scanner-pod` for this example.

    * Execute the Python script within the running pod, passing the Pokémon name as an argument:

        ```bash
        kubectl exec -it pokemon-scanner-pod -- python pokemon_fetcher.py pikachu
        ```

##   Explanation
    The application fetches data from the PokeAPI using the pokemon name provided as a command-line argument.
  
