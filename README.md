# Desafio Dio Recriando o Flappy Bird com Unity



**Projeto completo e abrangente para recriar o Flappy Bird com Unity:**



**Objetivo:** Criar um clone do jogo Flappy Bird usando o Unity.



### **Recursos:**

- **Unity Editor**

- **Script C#**

- **Sprites e sons do Flappy Bird**

  

### **Passos:**



**1. Crie um novo projeto do Unity.**



**2. Importe os sprites e sons do Flappy Bird para o projeto.**



**3. Crie um novo script chamado "FlappyBirdController".**



**4. Adicione o seguinte código ao script "FlappyBirdController":**



csharp



```csharp
using UnityEngine;
using System.Collections;

public class FlappyBirdController : MonoBehaviour
{
    public float jumpForce = 100f; // Força do pulo
    public float forwardSpeed = 2f; // Velocidade de avanço

    private Rigidbody2D rb; // Rigidbody do pássaro

    private void Start()
    {
        rb = GetComponent<Rigidbody2D>();
    }

    private void Update()
    {
        // Verifica se o jogador pressionou a tecla espaço
        if (Input.GetKeyDown(KeyCode.Space))
        {
            // Aplica uma força para cima ao pássaro
            rb.AddForce(Vector2.up * jumpForce);
        }
    }

    private void FixedUpdate()
    {
        // Move o pássaro para frente
        rb.velocity = new Vector2(forwardSpeed, rb.velocity.y);
    }
}
```



**5. Anexe o script "FlappyBirdController" ao pássaro.**



**6. Ajuste a força do pulo e a velocidade de avanço conforme desejado.**



**7. Crie um novo script chamado "PipeSpawner".**



**8. Adicione o seguinte código ao script "PipeSpawner":**

csharp



```csharp
using UnityEngine;
using System.Collections;

public class PipeSpawner : MonoBehaviour
{
    public GameObject pipePrefab; // Prefab do cano
    public float spawnRate = 1f; // Taxa de geração de canos em segundos
    public float pipeGap = 2f; // Espaço entre os canos

    private float nextSpawnTime; // Próximo momento em que um cano será gerado

    private void Start()
    {
        // Define o próximo momento em que um cano será gerado
        nextSpawnTime = Time.time + spawnRate;
    }

    private void Update()
    {
        // Verifica se é hora de gerar um cano
        if (Time.time >= nextSpawnTime)
        {
            // Instancia um cano
            Instantiate(pipePrefab, transform.position, Quaternion.identity);

            // Define o próximo momento em que um cano será gerado
            nextSpawnTime = Time.time + spawnRate;
        }
    }
}
```



**9. Anexe o script "PipeSpawner" a um objeto vazio na cena.**



**10. Ajuste a taxa de geração de canos e o espaço entre os canos conforme desejado.**



**11. Salve e execute o jogo.**



**Resultado:** Você terá um clone funcional do jogo Flappy Bird.



**Recursos adicionais:**



- Documentação da API do Unity para Rigidbody2D
- Tutorial da Unity sobre como criar um jogo de plataforma 2D

