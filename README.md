* We are running our app on the port 80. Time to create the deployment:
```
kubectl create -f deployment.yaml

```
* Verify that the app is running by doing `kubectl get` pods. 
* Now, let's expose our deployment so that it has an external IP through which it can receive traffic to the app:
```
kubectl expose deployment/myapp-deployment --type="LoadBalancer" --port 80
```
* Open browser and navigate to `http://localhost` to see the result

* Before we apply the change, open your terminal and do this:
```
while True
    do
        curl [Your IP Address]
        sleep 1s
    done
```
* Make sure you use your own external IP here. This will send a request to our app every second. Run it and you will see v1 content every second.
* Now, update version from version 1 to version. Let's apply our change:
```
kubectl apply -f deployment.yaml
```
* Make sure that our `while loop` check is running and saying that the v2 of our app is working. Let's apply our changes now and watch the while loop. After some time you will see that v1 start to run right after v2 without any delay.
