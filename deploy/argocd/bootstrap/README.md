# Argo CD Bootstrap
# Install Argo CD first, then apply root-app.yaml

# Step 1: Install Argo CD
# kubectl apply -n argocd -f https://raw.githubusercontent.com/argoproj/argo-cd/stable/manifests/install.yaml

# Step 2: Wait for pods to be ready
# kubectl wait --for=condition=available --timeout=300s deployment/argocd-server -n argocd

# Step 3: Get initial admin password
# kubectl -n argocd get secret argocd-initial-admin-secret -o jsonpath="{.data.password}" | base64 -d

# Step 4: Apply the root app-of-apps
# kubectl apply -f root-app.yaml

# Step 5: (Optional) Expose Argo CD UI via ingress
# kubectl apply -f argocd-ingress.yaml
