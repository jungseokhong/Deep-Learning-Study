# [Distort-and-Recover: Color Enhancement using Deep Reinforcement Learning](https://openaccess.thecvf.com/content_cvpr_2018/papers/Park_Distort-and-Recover_Color_Enhancement_CVPR_2018_paper.pdf)

_January 2021_; updated 02/12/21

tl;dr: Use deep reinforcement learning (DRL) and Markov decision process (MDP) to ehanche image color stepwise with a discort-and-recover strategy.

#### Overall impression
This paper proposes a way to ehance distorted images similar to a human expert; it is more explaninable and understandable than generative model based approaches. (e.g., pix-2-pix).

#### Key ideas
- Produce color-enhanced images using MDP, specifically Deep Q-Network (DQN).
- Present _distort-and-recover_training scheme to build distored-reference dataset without additional paired datasets.

#### Technical details
- Find optimimal sequence of image editing actions to ehance images, which minimizes a negative l2 distance between an image and corresponding target image. This can be considered as a MDP. The authors use a deep neural network as an agent to handle this problem.
- CNN (VGG-16) was used to extract context feature and Color histogram extracted color feature. The authors used a CIELab color histogram.
- state = (context feature, color feature) was fed to agent to decide an action A.
- L2 distance from the distorted image to the reference image stays between 10 and 20 in the CIELab color space.


#### Notes
- The number of actions for color enhancement was predefined. This could be a limiting factor.
- It was relatively easy to understand the idea.
- MDP/DRL-based approaches could be used in other domain.
- Worth checking MIT-Adobe FiveK dataset.
- [Automatic Photo Adjustment Using Deep Neural Networks](https://arxiv.org/pdf/1412.7725.pdf) (2015)
