# GCP
**To create cluster in GCP**
````
gcloud container clusters create my-cluster --num-nodes=3
````

**Authenticate GCP (gcloud auth application-default login)**

````
provider "google" {
  project = "your-gcp-project-id"
  region  = "us-central1"
}

resource "google_compute_instance" "vm_example" {
  name         = "terraform-vm"
  machine_type = "e2-micro"
  zone         = "us-central1-a"

  boot_disk {
    initialize_params {
      image = "debian-cloud/debian-11"
    }
  }
}
````
