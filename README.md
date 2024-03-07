# Adversarial_robustness
Adversarial robustness refers to a model's ability to resist being fooled.


1. Untargeted FGSM (Fast Gradient Sign Method):
   
Objective: The untargeted FGSM is an adversarial attack method used to generate adversarial examples that are misclassified by a model. The goal here is to maximize the model's loss with respect to the input image.

Procedure:
Compute the gradient of the loss function with respect to the input image.
Take the sign of the gradient to determine the direction in which the loss increases most rapidly.
Perturb the input image in that direction by a small step size (epsilon) to create the adversarial example.

Effectiveness: Untargeted FGSM is often effective at generating adversarial examples quickly. However, the generated adversarial examples may not always be highly targeted toward a specific misclassification.

2. Targeted FGSM (Fast Gradient Sign Method):
   
Objective: Targeted FGSM aims to generate adversarial examples that are specifically misclassified as a chosen target class.

Procedure:
Compute the gradient of the loss function with respect to the input image.
Instead of maximizing the loss, minimize the loss with respect to the target class.
Perturb the input image in the direction that minimizes the loss with respect to the target class by a small step size (epsilon).

Effectiveness: Targeted FGSM is often effective at generating adversarial examples that are misclassified as the specified target class. It can be used for targeted attacks in which the adversary aims to manipulate the model's predictions in a specific way.

3. Untargeted PGD (Projected Gradient Descent):
   
Objective: Untargeted PGD is an iterative adversarial attack method that iteratively perturbs an input image to maximize the model's loss. It is more powerful than FGSM as it considers multiple steps of perturbation.

Procedure:
Initialize the adversarial example with the original input image.
Compute the gradient of the loss function with respect to the input image.
Update the adversarial example in the direction of the gradient with a small step size ($\alpha$).
Clip the perturbed image to ensure it stays within an epsilon-ball around the original image.
Repeat steps 2-4 for a certain number of iterations or until convergence.

Effectiveness: PGD is more robust compared to FGSM as it performs multiple steps of gradient descent, which often results in stronger adversarial examples. It's commonly used for evaluating model robustness against adversarial attacks.

4. Targeted PGD (Projected Gradient Descent):
   
Objective: Targeted PGD is similar to untargeted PGD but aims to generate adversarial examples that are misclassified as a specific target class.

Procedure:
Compute the gradient of the loss function with respect to the input image.
Instead of maximizing the loss, minimize the loss with respect to the target class.
Update the adversarial example in the direction that minimizes the loss with respect to the target class, while ensuring it stays within an epsilon-ball around the original image.
Repeat steps 1-3 for a certain number of iterations or until convergence.

Effectiveness: Targeted PGD is effective at generating adversarial examples that are misclassified as the specified target class. It's often used for evaluating model robustness against targeted attacks and for generating adversarial examples for adversarial training.
These techniques are essential for understanding the vulnerabilities of deep learning models to adversarial attacks and for developing robust defense mechanisms against them.
