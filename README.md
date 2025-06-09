# SAR Image Colorization using Cycle-GAN Webapp

A Django web application for translating and colorizing Synthetic Aperture Radar (SAR) images using CycleGAN. Users can upload SAR or optical images, convert them using a pretrained CycleGAN model, and view/download results directly from the web interface.

## Features

- User registration and authentication (email-based)
- Upload SAR or optical images and convert between them (`SAR → Optical` or `Optical → SAR`)
- Powered by PyTorch and a ResNet-based CycleGAN model
- View, download, and manage your conversion history
- All image processing is performed securely on the backend

## Demo


![Screenshot 2025-05-15 202156](https://github.com/user-attachments/assets/5f9e73c8-2203-497c-bb50-8f44aa74a9e6)
![Screenshot 2025-05-15 202437](https://github.com/user-attachments/assets/2b4a6582-f506-4c52-bfed-e3d394656f8b)
![Screenshot 2025-05-15 204141](https://github.com/user-attachments/assets/bcb32aec-1144-4695-94fb-550d3870ef69)
![Screenshot 2025-05-15 202246](https://github.com/user-attachments/assets/d75ab20d-fd86-4936-a449-aed3a6e5bccb)
Add a screenshot if available -->

## Project Structure

```
project/
├── manage.py
├── db.sqlite3
├── req.txt
├── myapp/
│   ├── admin.py
│   ├── apps.py
│   ├── forms.py
│   ├── gan.py
│   ├── models.py
│   ├── path.py
│   ├── tests.py
│   ├── urls.py
│   └── views.py
├── media/
├── templates/
└── project/
    ├── __init__.py
    ├── asgi.py
    ├── settings.py
    ├── urls.py
    └── wsgi.py
```

## Installation

### 1. Clone the Repository

```bash
git clone https://github.com/NisanthV/SAR-image-colorization-using-Cycle-GAN-webapp.git
cd SAR-image-colorization-using-Cycle-GAN-webapp/project
```

### 2. Install Dependencies

It's recommended to use a Python virtual environment.

```bash
python3 -m venv venv
source venv/bin/activate
pip install -r req.txt
```

### 3. Download Pretrained Models

Place the pretrained CycleGAN generator weights (`G_A2B` and `G_B2A`) in the appropriate location as specified in `apps.py`. Make sure the model paths match.

### 4. Run Migrations

```bash
python manage.py migrate
```

### 5. Create a Superuser (optional)

```bash
python manage.py createsuperuser
```

### 6. Start the Development Server

```bash
python manage.py runserver
```

Visit `http://127.0.0.1:8000/` to use the webapp.

## Usage

1. Register or log in with your email.
2. Upload a SAR or optical image.
3. Select the conversion direction (`SAR → Optical` or `Optical → SAR`).
4. Submit and download/view your colorized or translated image.
5. Browse your upload and conversion history.

## Model Architecture

- Uses a ResNet-based CycleGAN generator for image translation.
- Model architecture is defined in `myapp/gan.py`.
- Inference is handled in `myapp/views.py` with PyTorch.

## Customization

- To use your own models, replace the weights and adjust the loading code in `apps.py`.
- UI templates can be customized in the `templates/` folder.

## Contributing

Pull requests and issues are welcome! Please open an issue for bug reports or feature requests.

-- Or your chosen license -->

## Acknowledgements

- [CycleGAN Paper](https://arxiv.org/abs/1703.10593)
- PyTorch
- Django
