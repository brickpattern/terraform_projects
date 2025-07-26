# README
 - in .github/workflows 
    - tried 2 different approaches 
    - terraform.yml 
        - this is doing the same steps i did locally via terraform that would run in github actions
        - this is failure bcos 
            - 
    - docker-build.yml
        - this is more right approach for container
        - this would fail bcos 
            - there is no Dockerfile natively in the repo.
            - the context .  would make the current working directory to expect a Dockerfile
            
    ```
        - name: Build and push Docker image
        id: build
        uses: docker/build-push-action@v4
        with:
          context: .
          push: true
          tags: |
            ${{ env.REGISTRY_URL }}/${{ env.IMAGE_NAME }}:latest
            ${{ env.REGISTRY_URL }}/${{ env.IMAGE_NAME }}:${{ github.sha }}
    ```
    - Disabled docker-build.yml and terraform.yml directly in github actions website. 