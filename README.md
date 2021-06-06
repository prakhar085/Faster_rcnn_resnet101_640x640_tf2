# Faster_rcnn_resnet101_640x640_tf2
Practical Implementation of Faster RCNN resnet 101 object detection tf2 API.

Notebook Brief.

1. Cloning TF2 Object Detection API from https://github.com/tensorflow/models if not already present.
2. Installing the API using %bash command.
3. Importing required libraries and pacakges.
4. Activating 
       
       model_builder_test.py
5. Creating a function to convert image file into numpy array.
   Puts image into numpy array to feed into tensorflow graph.
  Note that by convention we put it into a numpy array with shape
  (height, width, channels), where channels=3 for RGB.
6. Extracting traing data in form of tfrecord files(raccon), Here we used roboflow to create tfrecord file for custom tounges dataset.
   To create a dataset in Roboflow and generate TFRecords follow this https://blog.roboflow.ai/getting-started-with-roboflow/
   
7. Configure Faster RCNN Object Detection Training Configuration.


        'model_name': 'faster_rcnn_resnet101_v1_640x640_coco17_tpu-8',
        'base_pipeline_file': 'faster_rcnn_resnet101_v1_640x640_coco17_tpu-8.config',
        'pretrained_checkpoint': 'faster_rcnn_resnet101_v1_640x640_coco17_tpu-8.tar.gz',
        'batch_size': 6
        num_steps = 2000 #The more steps, the longer the training. Increase if your loss function is still decreasing and validation metrics are increasing. 
        num_eval_steps = 100 #Perform evaluation after so many steps
        
        
8. Train Custom TF2 Object Detector



              pipeline_file: defined above in writing custom training configuration
              model_dir: the location tensorboard logs and saved model checkpoints will save to
              num_train_steps: how long to train for
              num_eval_steps: perform eval on validation set after this many steps
              
              
9. Visualize the learning graph.
10. Run Inference on Test Images with Custom TensorFlow2 Object Detector

  Completed.
