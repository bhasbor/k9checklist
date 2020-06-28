### k8checklist
Kubernetes Security Audit Checklist

-	[ ]	Are you running all containers as a non-root user?
-	[ ]	Are you running any containers with the --privileged flag?
-	[ ]	Are you dropping capabilities that aren’t needed for each image?
-	[ ]	Are you running containers as read-only where possible?
-	[ ]	Are you checking for sensitive directories mounted from the host? How about the Docker socket?
-	[ ]	Are you running your CI/CD pipeline in your production cluster? Does it have privileged access or use the Docker socket?
-	[ ]	Are you scanning your container images for vulnerabilities?
-	[ ]	Do you have a process or tooling in place for rebuilding and redeploying containers where the image is found to include vulnerabilities?
-	[ ]	"Are you using a seccomp or AppArmor profile?
(The default Docker profiles are a good starting point; even better would be to shrink-wrap a profile for each application.)"
-	[ ]	If your host operating system supports SELinux, is it enabled? Do your applications have the right SELinux profiles attached?
-	[ ]	Is the contents of your base images/ Container image analyzed for unnecessary packages to reduce the attack surface?
-	[ ]	"Are you enforcing the use of immutable containers?
(Are you making sure that all executable code is added to a container image at build time and not installed at runtime?"
-	[ ]	Are you setting resource limits on your containers?
-	[ ]	Do you have admission control to make sure that only approved images can be instantiated in production?
-	[ ]	Are you using mTLS connections between components?
-	[ ]	Do you have a network policy restricting traffic between components?
-	[ ]	Are you passing secrets into containers using a temporary filesystem?
-	[ ]	Are your secrets encrypted at rest and in transit?
-	[ ]	Are you using a secrets management system for storage and rotation?
-	[ ]	Are you using a runtime protection tool to ensure that only expected executables are running inside containers?
-	[ ]	Do you have a runtime security solution for drift prevention?
-	[ ]	Are you using hosts exclusively for running containers, separate from other applications?
-	[ ]	Are you keeping your hosts systems up to date with the latest secrrity releases?
-	[ ]	Are you running an OS specifically designed for container hosts?
-	[ ]	Are you running regular checks on the security settings on the underlying cloud infrastructure using a CSPM tool?
-	[ ]	Are your hosts and container configured according to security best practices such as the CIS Benchmarks for Linux, Docker, and Kubernetes?
-	[ ]	Did you conducted security assessment for the application deployed inside the container?
