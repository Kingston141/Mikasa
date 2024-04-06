# Mikasa
using UnityEngine;

public class ShootingGallery : MonoBehaviour
{
    public GameObject targetPrefab;
    public Transform[] targetSpawnPoints;
    public float spawnInterval = 3f;
    public float gameDuration = 30f;

    private float spawnTimer;
    private float gameTimer;
    private bool isGameActive;

    void Start()
    {
        StartGame();
    }

    void Update()
    {
        if (isGameActive)
        {
            spawnTimer -= Time.deltaTime;
            gameTimer -= Time.deltaTime;

            if (spawnTimer <= 0f)
            {
                SpawnTarget();
                spawnTimer = spawnInterval;
            }

            if (gameTimer <= 0f)
            {
                EndGame();
            }
        }
    }

    void StartGame()
    {
        isGameActive = true;
        gameTimer = gameDuration;
        spawnTimer = spawnInterval;
    }

    void EndGame()
    {
        isGameActive = false;
        Debug.Log("Game Over! Your score: " + ScoreManager.score);
    }

    void SpawnTarget()
    {
        int spawnPointIndex = Random.Range(0, targetSpawnPoints.Length);
        Vector3 spawnPosition = targetSpawnPoints[spawnPointIndex].position;
        Quaternion spawnRotation = targetSpawnPoints[spawnPointIndex].rotation;
        Instantiate(targetPrefab, spawnPosition, spawnRotation);
    }
}
