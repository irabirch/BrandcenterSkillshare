# BrandcenterSkillshare

Create a script called "Shapespawner". Make sure the name matches exactly. 

In the text document (or, if you're using it, Visual Studio/other coding software), copy and paste the script in between the lines below:

----------


using System.Collections;
using System.Collections.Generic;
using UnityEngine;

public class Shapespawner : MonoBehaviour
{
    public Shape[] shapesPrefabs;

    float forcePlus = 5.8f;

    // Start is called before the first frame update

    void Start()
    {
        //Debug.Log("Press the left arrow " + numberOfTimes + " times to go left at the speed of " + theSpeedOf);
    }

    // Update is called once per frame
    void Update()
    {
        Instantiator();
        ForceIncreaser();
    }

    private void ForceIncreaser()
    {
        if (Input.GetKeyDown(KeyCode.F))
        {
            for (int i = 0; i < shapesPrefabs.Length; i++)
            {
                shapesPrefabs[i].IncreaseForce(forcePlus);
            }

        }
    }

    private void Instantiator()
    {
        if (Input.GetKeyDown(KeyCode.Space))
        {
            for (int i = 0; i < shapesPrefabs.Length; i++)
            {
                Instantiate(shapesPrefabs[i]);
            }
        }
    }
}


Shape

using System.Collections;
using System.Collections.Generic;
using UnityEngine;

public class Shape : MonoBehaviour
{
    float forceMagnitude = 5.8f;
    Material shapeMaterial;
    Rigidbody myRigidBody;
    // Start is called before the first frame update
    void Start()
    {
        shapeMaterial = GetComponent<MeshRenderer>().material;
        myRigidBody = GetComponent<Rigidbody>();

    }

    // Update is called once per frame
    
    public void IncreaseForce(float addedForce)
    {
        forceMagnitude += addedForce;
    }


}

  ----------
