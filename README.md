# istio-for-canary-deployment
Install Istio
Download Istio:
curl -L https://istio.io/downloadIstio | sh -
Enter the extracted directory:
cd istio-*
Add istioctl to PATH:
export PATH=$PWD/bin:$PATH
Install Istio:
istioctl install --set profile=demo -y
istioctl install --set meshConfig.accessLogFile=/dev/stdout
Verify:
kubectl get pods -n istio-system

You should see pods such as:

istiod-xxxxx
istio-ingressgateway-xxxxx
Verify CRDs:
kubectl get crd | grep destinationrules

Expected output:

destinationrules.networking.istio.io
next chnage cd:
cd ..
now create destination yaml:
kubectl apply -f " our destination file name with extention .yaml or .yml"
